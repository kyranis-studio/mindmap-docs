**Instruction:**\
You are tasked with updating a configuration system for leave types within an absence management module. Follow these steps precisely:

1. **Add Fields:**

   * In the `leavetype` and the "Local settings -> absences and provisions" tab, specifically the "Absence type" tab, introduce three new fields:

     * `multiple`: `SMALL INT UNSIGNED NULL`

     * `iscyclerestricted`: `TINYINT UNSIGNED NOT NULL` (default `0`)

     * `isfractionnable`: `TINYINT UNSIGNED NOT NULL` (default `0`)

2. **Set Values:**

   * For individual center leave types (CA), set `multiple` to `2`.

   * For all other leave types, set `multiple` to `1`.

   * If `multiple` is `NULL`, treat it as `1`.

3. **Configuration for CA Absence Types:**

   * Set `iscyclerestricted` to `1` for CA absence types.

   * Set `isfractionnable` to `1` for CA absence types.

4. **Manage Absences V2:**

   * **Date-by-Date Submissions:** If `isfractionnable` is `1`, enable date-by-date submissions. Display a list of selected dates at the bottom with options to delete individual dates or all dates simultaneously.

   * **Cycle Restriction:** If `iscyclerestricted` is `1` for the selected absence type, restrict selectable dates to the cycle of the chosen date after the agent selects a date.

   * **Multiple Day Validation:** If `multiple` is set (not `NULL`) and not equal to `1`, display a red error message on the capture screen:\
     `"The number of days taken must be a multiple of {multiple}"`\
     Ensure this validation is performed server-side; client-side validation should not be relied upon. If the condition is violated, the save operation must fail and display the same error message to the user.

**Desired Output:**
Provide the updated configuration details as specified, ensuring all logical steps and error handling are accurately implemented without any additional explanatory text.

For individual centers (this characteristic can also be applied to the absence type for individual centers (CAPE GOBET for LFOB)), days off must be able to be requested individually, with a list of selected dates displayed at the bottom, and the ability to delete each date individually or all dates at once. A parameter must also be added to \`leavetype\`: \`SMALL INT(2) UNSIGNED NULL\` by default, named "multiple". Set this to 2 for the leave types for individual centers. Individual centers are found in the \`centerdetail\` table with \`organisationtype=individual\`. If \`multiple\` is set to 2, only an even number of dates should be accepted. The third point is that we have introduced the concept of a 28 or 30-day cycle for Individual Centers (CI).

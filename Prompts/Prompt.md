env \
LD\_LIBRARY\_PATH="/usr/local/lib/ollama/cuda\_v12:\$LD\_LIBRARY\_PATH" \
BONSAI\_CTX=4096 \
BONSAI\_NGL=10 \
./scripts/start\_llama\_server.sh

export BUILDKIT_NO_CLIENT_TOKEN=1

export DOCKER_BUILDKIT=1
export COMPOSE_DOCKER_CLI_BUILD=1

<!-- Add line when use cat command -->

conditional_newline() {
local IFS='['
read -sdR -p $'\E[6n' POS
    local COL="${POS#\*;}"
if [ "$COL" -ne 1 ]; then
echo ""
fi
}
PROMPT_COMMAND="conditional_newline; $PROMPT_COMMAND"

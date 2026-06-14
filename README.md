RED='\033[31m'
GREEN='\033[32m'
YELLOW='\033[33m'
RESET='\033[0m'

# Root权限验证
if [ "$(id -u)" -ne 0 ]; then
    echo -e "${RED}\n必须使用Root权限执行!${RESET}"
    exit 1
fi

# 检查 ssh-keygen
if ! command -v ssh-keygen &>/dev/null; then
    echo -e "${RED}\n请使用 MT 管理器扩展包环境执行！${RESET}"
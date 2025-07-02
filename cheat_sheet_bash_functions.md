# Bash Scripting — Functions Basics

```bash
#!/usr/bin/env bash
#######################################
#   BASH FUNCTION QUICK‑REFERENCES    #
#######################################

# List currently‑defined functions
declare -F

# --- Defining functions ---------------------------------
greet() {                 # classic form
  local name=${1:-"world"}
  echo "Hello, $name!"
}

function add_numbers() {  # alternate form
  echo "$(( $1 + $2 ))"
}

# --- Returning values -----------------------------------
result=$(add_numbers 3 4)   # capture stdout
echo "Sum = $result"

# --- Raising errors -------------------------------------
fail_if_empty() {
  [[ -z $1 ]] && return 1
}
if ! fail_if_empty "$result"; then
  echo "error: empty value" >&2
fi

# --- Recursive example ----------------------------------
factorial() {
  (( $1 <= 1 )) && { echo 1; return; }
  local prev=$(factorial $(($1 - 1)))
  echo $(($1 * prev))
}

# Safe‑guard against fork bombs
ulimit -u 100
```

Key points ⬇︎

| Topic          | Tip                                 |
| -------------- | ----------------------------------- |
| Passing args   | `$1`, `$2`, `"$@"` (all)            |
| Returning data | Echo + capture; or `printf -v`      |
| Local vars     | `local var=value` (bash‑only)       |
| Exit status    | `return <0‑255>`; `0` = success     |
| Error handling | `set -euo pipefail` for strict mode |

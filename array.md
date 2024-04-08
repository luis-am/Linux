output=$(ls .)

readarray -t lista <<< "$output"

for i in "${lista[@]}"; do
    echo "$i"
done

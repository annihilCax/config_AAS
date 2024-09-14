### Задача 1
```bash
cut -f1 -d: /etc/passwd | sort | cat -n
```
<img width="368" alt="image" src="https://github.com/user-attachments/assets/e1b00efb-55ab-4730-b3cb-20962ecc8c7d">


### Задача 2
```bash
cat /etc/protocols | tail -n 5 | sort -k2 | awk '{print $2, $1}'
```
<img width="491" alt="image" src="https://github.com/user-attachments/assets/772fb488-9228-47be-9c5a-d022b2738528">

### Задача 3
```bash
#!/bin/bash
text=$*
length=${#text}
for _ in $(seq 1 $((length + 2))); do line+="-"
done
echo "+${line}+"
echo "| ${text} |"
echo "+${line}+"
```
<img width="242" alt="image" src="https://github.com/user-attachments/assets/bdc4cedd-ccfa-4856-8b32-31ec544a4e59">

### Задача 4
```bash
#!/bin/bash
file="$1"
ids=$(grep -o -E '\b[a-zA-Z]*\b' "$file" | sort -u)
echo "$ids"
```
<img width="325" alt="image" src="https://github.com/user-attachments/assets/45626d71-a952-4e18-984a-51abe4b1a95a">

### Задача 5
```bash
#!/bin/bash
file=$1
chmod 755 "./$file"
sudo cp "$file" /usr/local/bin
echo "'$file'. Готово"
```
<img width="256" alt="image" src="https://github.com/user-attachments/assets/86963858-42b1-4a24-aecd-53d6bfd6b744">


### Задача 6
```bash

```

### Задача 7
```bash

```

### Задача 8 
```bash

```

### Задача 9
```bash

```

### Задача 10
```bash

```


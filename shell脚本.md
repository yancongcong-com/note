```shell
#!/usr/bin/bash
while  [  $# -ne 0 ]
do
	let  sum+=$1
	shift  #参数位置左移
done
echo "sum: $sum"


```


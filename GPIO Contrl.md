# GPIO

## export
### /sys/class/gpio# echo 44 > export
## set direction
### /sys/class/gpio/gpio44# echo out > direction

## 4. 设置输出
### /sys/class/gpio/gpio44# echo 1 > value
## 5. 查看输出值
### /sys/class/gpio/gpio44# cat value
## 6. 取消导出
### /sys/class/gpio# echo 44 > unexport

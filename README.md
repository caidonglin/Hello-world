# Hello-world
我在GitHub上的首个仓库
#!/bin/bash
#filename:
#author:
#date:2018-6-6
echo "用户管理程序"
echo "1.创建用户"
echo "2.删除用户"
echo "3.锁定用户"
echo "4.解锁用户"
echo "5.退出脚本"

read -p "请输入您的操作选择(1-5)：" sn
case $sn in
1)
read -p "请输入创建用户名：" nu
useradd $nu
echo "123456" | passwd --stdin $nu
if [ '$?' == '0' ];
then
echo "用户已经创建成功"
exit
       fi

;;

2)
read -p "请输入要删除用户名：" nl
userdel $nl
echo "已经删除$nl用户"

if
[ $? -ne 0 ];
then
echo "成功删除"
fi
;;

3)
STAT=$(passwd -S $use | awk '{print $2}') 
read -p "锁定用户" use
if [ '$STAT' == "PS" ];
then
passwd -l $use 
fi
if [ '$STAT' == "LK" ];
then
echo "已经锁定用户"
exit
fi
;;

4)
read -p "解锁用户" jie
echo $jie 
if [ '$STAT' == "LK" ];
then
passwd -u $jie
fi
if [ '$STAT' == "LK" ];
then
echo "已经解锁用户"
exit
fi
;;
5)
if [ $sn == 5 ];
then
read -p "是否退出(yes)" tu
if [ $tu == yes  ];
then
    exit 
fi

fi

esac

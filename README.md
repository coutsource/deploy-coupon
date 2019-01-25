h5:
```
git clone https://github.com/coutsource/h5-coupon.git
cd h5-coupon/
npm install
npm run build 
scp -r dist/ root@${ip}:/root/www/  (替换服务器上dist目录即可)
```

admin:
```
git clone https://github.com/coutsource/admin-coupon.git

mv admin-coupon/ laravel-shop/
cd laravel-shop/
composer install
npm install

cd ..
tar -zcf laravel-shop.tar laravel-shop/

scp laravel-shop.tar  root@${ip}:/root/www/  (替换服务器上的larave-shop.tar, 并且解压，替换服务器下的laravel-shop目录即可)
(注意目录下的laravel-shop目录下的.env文件使用服务器上已有的/root/www/.env文件)
```

服务器：
```
替换完目录后，修改文件夹权限，重启docker容器
chmod -R 777 laravel-shop/storage

docker restart webserver
```

####获取jd_cookie新方法


docker run -d -p 29099:29099  scjtqs/jd_cookie:latest

## 更新镜像
docker pull jd_cookie scjtqs/jd_cookie:latest
## UPSAVE 默认是空，不会推送到其他地址；DB_ENABLE默认为false，不会记录cookie到db。
docker run -d \
-p 29099:29099 \
-e UPSAVE="http://192.168.0.12:8080/savecookie" \
-e DB_ENABLE="true" \
-e DB_HOST="192.168.0.13" \
-e DB_PORT="3306" \
-e DB_USER="root" \
-e DB_PASS="abcde" \
-e DB_DATABASE="cookies" \
-e DB_TYPE="mysql" \
--name jd_cookie scjtqs/jd_cookie:latest
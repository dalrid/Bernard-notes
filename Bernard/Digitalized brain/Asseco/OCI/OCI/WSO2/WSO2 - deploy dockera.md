cd /sandbox/wso2 && rm wso2.tar.gz && tar zcvf wso2.tar.gz wso2 && docker build -t wso2_image_20240928_am_bk_proddb-v2 . && docker run -d --name wso2_image_20240928_am_bk_proddb-v2 -p 9444:9443 -p 8090:8090 wso2_image_20240928_am_bk_proddb-v2

docker login fra.ocir.io

docker tag wso2_image_20240928_am_bk_proddb fra.ocir.io/frkvgr6rogi5/wso-2/wso2_image_20240928_am_bk_proddb


Nowy server 

cd /sandbox/wso2 && rm wso2.tar.gz && tar zcvf wso2.tar.gz wso2 && docker build -t wso2_image_20240928_am_bk_proddb-v4_smtp . && docker run -d --name wso2_image_20240928_am_bk_proddb-v4_smtp -p 9444:9443 -p 8090:8090 wso2_image_20240928_am_bk_proddb-v4_smtp



docker container stop wso2_image_20240928_am_bk_proddb-v4_smtp && docker container rm wso2_image_20240928_am_bk_proddb-v4_smtp && docker image rm wso2_image_20240928_am_bk_proddb-v4_smtp

FROM avc-service
# 签名啦
MAINTAINER openedbox "openedbox@qq.com"


RUN mkdir -p /opt/gitblit
ADD gitblit-1.6.2.tar.gz /opt/gitblit/
run mkdir -p /opt/gitblit-data
run mv /opt/gitblit/data/* /opt/gitblit-data
run mv /opt/gitblit-data/gitblit.properties /opt/gitblit-data/default.properties

run sed -e "s/server\.httpsPort\s=\s8443/server\.httpsPort=443/" \
        -e "s/server\.httpPort\s=\s0/server\.httpPort=80/" \
        -e "s/server\.redirectToHttpsPort\s=\sfalse/server\.redirectToHttpsPort=true/" \
        -e "s/web\.enableRpcManagement\s=\sfalse/web\.enableRpcManagement=true/" \
        -e "s/web\.enableRpcAdministration\s=\sfalse/web.enableRpcAdministration=true/" \
        /opt/gitblit-data/default.properties > /opt/gitblit-data/gitblit.properties

# Setup the Docker container environment and run Gitblit
workdir /opt/gitblit
expose 80
expose 443
expose 9418
expose 29418
cmd ["java", "-server", "-Xmx1024M", "-Djava.awt.headless=true", "-jar", "/opt/gitblit/gitblit.jar", "--baseFolder", "/opt/gitblit-data"]

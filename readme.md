docker run -u zap \
  -v $(pwd)/zap-reports:/zap/wrk \
  -p 8090:8090 \
  -d zaproxy/zap-stable zap.sh -daemon \
  -host 0.0.0.0 -port 8090 \
  -config api.addrs.addr.name=.* \
  -config api.addrs.addr.regex=true \
  -config api.key=mysecretkey123

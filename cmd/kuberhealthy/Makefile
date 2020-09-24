# IMAGE="jlmatias/kuberhealthy"
TAG="v2.2.2"

build:
	docker build -t jlmatias/kuberhealthy:$(TAG) -f Dockerfile ../../

push:
	docker push jlmatias/kuberhealthy:$(TAG)

test:
	POD_NAME="kuberhealthy-test" go test -run TestWebServer -v -args -- --debug --forceMaster
run:
	go build
	POD_NAME="kuberhealthy-test" ./kuberhealthy --debug --forceMaster
run-influx:
	go build
	POD_NAME="kuberhealthy-test" ./kuberhealthy -debug -forceMaster -enableInflux -influxUrl=http://localhost:8086 -influxDB=kuberhealthy

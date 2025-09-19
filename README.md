# CameraIntegrationGrafana
Integration of videocamera panels in Grafana using a central VPN server and without the need of any type of proxy


The objective is to be able to visualize video cameras inside any Grafana panels. 
This was also done in a cloud server that serves as a OpenVPN server aswell whose clients are the routers to which the cameras are connected.

enable camera rtsp streaming
port redirection from router to rtsp port of camera
go2rtc add camera stream to streamings
https needed for grafana panel, grafana does not trust http and blocks video
go2rtc add https port, https certs, 
problem with go2rtc auth, basic auth works but grafana iframe cannot auth
dont want to use reverse proxie allowing only streams links so solution: put static_dir to control what can be seen, copy www directory of github repository to web, move htmls that dont conflict with webrtc stream and we dont want them to show, finally custom index.html to avoid showing all the contents of the folder
add rules to cloud server windows firewall plus cloud server provider firewall to allow https port of go2rtc
grafana video plugin + add link to strem in iframe
nssm to make it a windows service


The real tests were done with:
- go2rtc v
- Reolink Cameras
- Grafana v
- 
- nssm v

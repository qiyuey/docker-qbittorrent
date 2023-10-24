# 自用
```yaml
version: "3.5"
services:
  qbittorrent:
    image: qiyuey/qbittorrent
    container_name: qbittorrent
    environment:
      - PUID=1000
      - PGID=100
      - TZ=Asia/Shanghai
      - UT=true
      - TL=https://fastly.jsdelivr.net/gh/XIU2/TrackersListCollection/best.txt
    volumes:
      - /share/Public/Docker/qbittorrent:/config
      - /share/Archive/Downloads:/downloads
      - /share/Public/Data/Tech:/cert
    ports:
      - 6881:6881
      - 6881:6881/udp
      - 6363:6363
    restart: unless-stopped
```
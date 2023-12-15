# Get NordVPN WireGuard Config

Use docker compose to construct wireguard config for NordVPN connections

## Usage
- Copy .env.example to .env `cp .env.example .env`
- Update TOKEN variable within .env
- API_QUERY for server has basic filters but can be changed as needed
- DNS_SERVER is set to quad9 but can also be changed as needed
- Start with compose `docker-compose up -d`
- Config is available in output directory and container logs `docker logs nordvpn_get_wireguard_config`
- Remove the container `docker-compose down`

## Links
[Script is based on this gist and its comments ](https://gist.github.com/bluewalk/7b3db071c488c82c604baf76a42eaad3)

[Docker image is based on this NordVPN support article](https://support.nordvpn.com/Connectivity/Linux/1507838432/How-to-build-the-NordVPN-Docker-image.html)

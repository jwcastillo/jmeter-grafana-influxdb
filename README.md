<h1 align="center">Welcome to Jmeter | Influx | Grafana | Docker 👋</h1>
<p>
  <img src="https://img.shields.io/badge/version-v0-blue.svg?cacheSeconds=2592000" />
  <a href="/docs">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" target="_blank" />
  </a>
  <a href="LICENSE">
    <img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg" target="_blank" />
  </a>
  <a href="https://twitter.com/jwcastillo">
    <img alt="Twitter: jwcastillo" src="https://img.shields.io/twitter/follow/jwcastillo.svg?style=social" target="_blank" />
  </a>
</p>

> Stack to running loadtests with Jmeter, Influx, Grafana in Containers! 

## Dashboard Demo

Edit this dashboard on `grafana/dashboards/jmeter-cnt.json`

![demo1](.github/images/demo1.png)

![demo1](.github/images/demo2.png)

## HTTP Test Example

Put your `.jmx`file on `test/default_test_plan.jmx` or change the environment variable `JMETER_TEST` on `docker-compose.yml` with your filename

## Influxdb Tunning

Edit `influxdb/influx.conf`

### 🏠 [Homepage](/)

## Build

```sh
docker-compose build
```
## Usage

### Run Grafana & Influxdb
```sh
docker-compose up grafana influxdb -d
```

### Run tests
```sh
docker-compose up jmeter
```


### Monitoring
Access Grafana Dashboards on

```sh
htt://localhost:3000
```

## Author

👤 **Wenceslao Castillo**

* Twitter: [@jwcastillo](https://twitter.com/jwcastillo)
* Github: [@jwcastillo](https://github.com/jwcastillo)

### Work based on:

👤 **Matheus Fidelis**

* Twitter: [@fidelissauro](https://twitter.com/fidelissauro)
* Github: [@msfidelis](https://github.com/msfidelis)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](/issues).

## Show your support

Give a ⭐️ if this project helped you!

## 📝 License

Copyright © 2020 [Matheus Fidelis](https://github.com/msfidelis).<br />
This project is [MIT](LICENSE) licensed.

***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
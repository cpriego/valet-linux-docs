<p align="center"><img src="https://cdn.rawgit.com/wiki/cpriego/valet-linux/images/valet.svg"></p>

## Introduction

Valet *Linux* is a Laravel development environment for Linux minimalists. No Vagrant, no `/etc/hosts` file. You can even share your sites publicly using local tunnels. _Yeah, we like it too._

Valet *Linux* configures your system to always run Nginx in the background when your machine starts. Then, using [DnsMasq](https://en.wikipedia.org/wiki/Dnsmasq), Valet proxies all requests on the `*.test` domain to point to sites installed on your local machine.

In other words, a blazing fast Laravel development environment that uses roughly 7mb of RAM. Valet *Linux* isn't a complete replacement for Vagrant or Homestead, but provides a great alternative if you want flexible basics, prefer extreme speed, or are working on a machine with a limited amount of RAM.

## Official Documentation

Documentation for Valet can be found on the [Valet Linux website](https://cpriego.github.io/valet-linux-docs/).

## License

Laravel Valet is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)

# Contributing
*To help us improve the site:*

1.Fork it

2.Create your feature branch (git checkout -b my-new-feature)

3.Commit your changes (git commit -am 'Add some feature')

4.Push to the branch (git push origin my-new-feature)

5.Create new Pull Request


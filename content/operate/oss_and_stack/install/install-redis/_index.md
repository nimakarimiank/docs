
## Redis

This is a an installation guide. You'll learn how to install, run, and experiment with the Redis server process.

While you can install Redis on any of the platforms listed below, you might also consider using Redis Cloud by creating a [free account](https://redis.com/try-free?utm_source=redisio&utm_medium=referral&utm_campaign=2023-09-try_free&utm_content=cu-redis_cloud_users).

## Install Redis

How you install Redis depends on your operating system and whether you'd like to install it bundled with Redis Stack and Redis UI. See the guide below that best fits your needs

## Test if you can connect using the CLI

to make hacking with Redis simpler, Redis provides a command line utility that can be used to send commands to Redis. This program is called **redis-cli**.

The first thing to do to check if Redis is working properly is sending a **PING** command using redis-cli:

```
$ redis-cli ping
PONG
```

Running **redis-cli** followed by a command name and its arguments will send this command to the Redis instance running on localhost at port 6379. You can change the host and port used by `redis-cli` - just try the `--help` option to check the usage information.

Another interesting way to run `redis-cli` is without arguments: the program will start in interactive mode. You can type different commands and see their replies.

```
$ redis-cli
redis 127.0.0.1:6379> ping
PONG
```
## Install on Ubuntu/Debian
Prerequisites:

If you're running a very minimal distribution (such as a Docker container) you may need to install  `lsb-release`,  `curl`  and  `gpg`  first:

```bash
sudo apt install lsb-release curl gpg
```
Add the repository to the  `apt`  index, update it, and then install:

```bash
curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list

sudo apt-get update
sudo apt-get install redis
```
# Install Redis on Windows

Use Redis on Windows for development

Redis is not officially supported on Windows. However, you can install Redis on Windows for development by following the instructions below.

To install Redis on Windows, you'll first need to enable  [WSL2](https://docs.microsoft.com/en-us/windows/wsl/install)  (Windows Subsystem for Linux). WSL2 lets you run Linux binaries natively on Windows. For this method to work, you'll need to be running Windows 10 version 2004 and higher or Windows 11.

## Install or enable WSL2

Microsoft provides  [detailed instructions for installing WSL](https://docs.microsoft.com/en-us/windows/wsl/install). Follow these instructions, and take note of the default Linux distribution it installs. This guide assumes Ubuntu.

## Install Redis

Once you're running Ubuntu on Windows, you can follow the steps detailed at  [Install on Ubuntu/Debian](https://redis.io/docs/latest/operate/oss_and_stack/install/install-redis/install-redis-on-linux/#install-on-ubuntu-debian)  to install recent stable versions of Redis from the official  `packages.redis.io`  APT repository. Add the repository to the  `apt`  index, update it, and then install:

```bash
curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list

sudo apt-get update
sudo apt-get install redis
```

Lastly, start the Redis server like so:

```bash
sudo service redis-server start
```

## Connect to Redis

You can test that your Redis server is running by connecting with the Redis CLI:

```bash
redis-cli 
127.0.0.1:6379> ping
PONG
```

You can also test that your Redis server is running using  [Redis Insight](https://redis.io/docs/latest/develop/connect/insight/)  for easier access.


## Test if you can connect using the CLI

After you have Redis up and running, you can connect using  `redis-cli`.

External programs talk to Redis using a TCP socket and a Redis specific protocol. This protocol is implemented in the Redis client libraries for the different programming languages. However, to make hacking with Redis simpler, Redis provides a command line utility that can be used to send commands to Redis. This program is called  **redis-cli**.

The first thing to do to check if Redis is working properly is sending a  **PING**  command using redis-cli:

```
$ redis-cli ping
PONG

```

Running  **redis-cli**  followed by a command name and its arguments will send this command to the Redis instance running on localhost at port 6379. You can change the host and port used by  `redis-cli`  - just try the  `--help`  option to check the usage information.

Another interesting way to run  `redis-cli`  is without arguments: the program will start in interactive mode. You can type different commands and see their replies.

```
$ redis-cli
redis 127.0.0.1:6379> ping
PONG

```

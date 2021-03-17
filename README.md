# AskBob Plugin Skeleton

A skeleton Ask Bob plugin.

## Docker

**AskBob** can be built as a server (with voice WAV upload functionality enabled) using the Docker configurations provided.

### Building the Docker container

**AskBob** can be built without support for voice queries with `docker-compose` using the following command:
```bash
$ docker-compose build voiceless
```

Similarly, **AskBob** can be built with such support using the following command:
```bash
$ docker-compose build voice
```

An additional build-time configuration (JSON) may be specified using a build argument, e.g.
```bash
$ docker-compose build --build-arg ASKBOB_SETUP_CONFIG=default_config.json voice
```

### Usage

The **AskBob** server can then be launched using the following commands:

- voice mode
```bash
$ docker-compose up voice

```
- voiceless mode
```bash
$ docker-compose up voiceless
```

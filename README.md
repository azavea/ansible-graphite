# ansible-graphite

An Ansible role for installing [Graphite](http://graphite.wikidot.com).

## Role Variables

- `graphite_carbon_version` - Carbon version
- `graphite_whisper_version` - Whisper version
- `graphite_web_version` - Graphite Web version
- `graphite_home` - Default directory for Graphite (default: `/opt/graphite`)
- `graphite_web_port` - Default Apache virtual host port for Graphite Web (default: `8080`)
- `graphite_web_secret_key` - The value of `SECRET_KEY` for Graphite Web (default: `SECRET`)

## Example Playbook

First, ensure that you override `graphite_web_secret_key` with a random string. This is used by the Graphite Web Django application for salting hashes used in auth tokens, CRSF middleware, cookie storage, etc.

The other bit of important information is the default administrator credentials for the Graphite Web Django application:

Username: `admin@example.com`  
Password: `admin`

You can changes these after the installation completes with:

```bash
$ sudo python manage.py changepassword admin
```

See the [examples](./examples/) directory for more details.

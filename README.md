# PyDroneio  [![Build Status](https://cloud.drone.io/api/badges/tinvaan/PyDroneio/status.svg)](https://cloud.drone.io/tinvaan/PyDroneio)
Python client for the [Drone CI](https://cloud.drone.io) public [remote api](https://readme.drone.io/api/overview/) built using the popular [python requests](https://pypi.org/project/requests/) library.

## Installation
Ensure you have a working installation of Python 3.x on your system.  
Clone the repository and run the setup script provided.
```bash
$ git clone https://github.com/tinvaan/PyDroneio.git
$ cd PyDroneio
$ python setup.py install
```

## Usage examples

Fetch all linked repos
```python
>>> from drone import drone
>>> client = drone('tinvaan', 'packager')
>>> client.repos.all()
[{'id': 799963,
  'uid': '45485693',
  'user_id': 0,
  'namespace': 'tinvaan',
  'name': 'Algorithms',
  'slug': 'tinvaan/Algorithms',
    ...
    ...
  'version': 1},

    ...
    ...
    ...

 {'id': 7993143,
  'uid': '1897133997',
  'user_id': 0,
  'namespace': 'tinvaan',
  'name': 'zeit-logdna',
  'slug': 'tinvaan/zeit-logdna',
    ...
    ...
  'version': 1}]

```

Add a new secret
```python
>>> secret = {
        'name': 'testsecret',
        'data': 'mysecretvalue',
        'pull_request': False
   }
>>> client.secret.create(**secret)
{'id': 55114, 'repo_id': 7134978, 'name': 'testsecret'}
```

Fetch all builds for a repository
```python
>>> client.build.all()
[{'id': 342416, ... 'version': 3},
 {'id': 342400, ... 'version': 3},
 {'id': 341144, ... 'version': 3}]

```

## Contribute
If you notice any issues, bugs or missing features in this project, please feel free to open tickets(github issues) or pull requests for the same.

If you would like to contribute code, check out the open issues and if you need help getting started, shoot a mail to harishnavnit@gmail.com 
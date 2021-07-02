<!--
 Licensed to the Apache Software Foundation (ASF) under one
 or more contributor license agreements.  See the NOTICE file
 distributed with this work for additional information
 regarding copyright ownership.  The ASF licenses this file
 to you under the Apache License, Version 2.0 (the
 "License"); you may not use this file except in compliance
 with the License.  You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

 Unless required by applicable law or agreed to in writing,
 software distributed under the License is distributed on an
 "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
 KIND, either express or implied.  See the License for the
 specific language governing permissions and limitations
 under the License.
 -->

# Jupyterlab Helm Chart

This chart lets you install a single user instance of jupyterlab into a kubernetes cluster.

There are more elaborate solutions out there (see [jupyterhub](https://zero-to-jupyterhub.readthedocs.io/en/stable/))
, but sometimes this is all you need. 

# Features

## Python requirements

Additional python requirements can be installed with helm config (see `pythonRequirements`).

## Extra python files

You can inject additional python files (e.g. containing helper functions) using `extraConfigMapFiles`

For example:

```yaml
extraConfigMapFiles:
  my_utils.py: |
    def print_hello():
        print("hello")
```

Then use in any notebook like so:

```python
from my_utils import print_hello

print_hello()
```
## S3 backend

You can use s3 as a storage backend for your notebooks.  See `s3` in `values.yaml`.

# Acknowledgements

This chart was inspired by [Deepak Sood's](https://medium.com/@deepaksood619) medium post 
[Deploying Standalone JupyterLab on Kubernetes for Early Stage Startups](https://medium.com/analytics-vidhya/deploying-standalone-jupyterlab-on-kubernetes-for-early-stage-startups-7a1468fae289).

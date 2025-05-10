# repro-pants-debugger-issue

## How to repro

1. Clone the repo
2. Run

   ```bash
   pants package src/webapp:pex_binary
   ```

   ```text
   22:26:49.84 [INFO] Completed: Building 79 requirements for src.webapp/pex_binary.pex from the 3rdparty/python/python-default.lock resolve: SQLAlchemy<2.0.0,>=1.4, aiohttp<4.0.0,>=3.11.2, alembic<2.0.0,>=1.8.0, authlib<2.0.0,>=1.2,... (1918 characters truncated)
   22:26:49.84 [ERROR] 1 Exception encountered:
   
   Engine traceback:
     in `package` goal
   
   ProcessExecutionFailure: Process 'Building 79 requirements for src.webapp/pex_binary.pex from the 3rdparty/python/python-default.lock resolve: SQLAlchemy<2.0.0,>=1.4, aiohttp<4.0.0,>=3.11.2, alembic<2.0.0,>=1.8.0, authlib<2.0.0,>=1.2, azure-core<2.0.0,>=1.25.0, azure-identity, azure-servicebus, azure-storage-blob<13.0.0,>=12.16.0, bleach<7.0.0,>=6.0.0, boto3==1.35.99, botocore<2.0.0,>=1.35.99, cachetools<6.0.0,>=5.3.2, celery[redis]<6.0.0,>=5.4.0, connexion[swagger-ui]<3.0.0,>=2.14, country-converter<2.0.0,>=1.0, cryptography<45.0.0,>=42.0.5, databricks-cli==0.18.0, databricks-sql-connector<3.0.0,>=2.0.5, datadog<1.0.0,>=0.48.0, ddtrace<3.0.0,>=2, debugpy~=1.8.11, docker<8.0.0,>=7.1.0, editdistance<0.7.0,>=0.6.2, flask-compress<2.0.0,>=1.12, flask-cors<5.0.0,>=4.0.2, flask==2.2.5, flask_testing<0.9.0,>=0.8, flower<2.0.0,>=1.2.0, fpdf2<3.0.0,>=2.8.2, gunicorn<23.0.0,>=22.0, hvac<0.11.0,>=0.10, inflect<7.0.0,>=6.0.4, jsonschema<5.0.0,>=4.10, mergedeep<2.0.0,>=1.3.4, moto[s3,sqs]<5.0,>=3.0, mypy-boto3-quicksight<2.0.0,>=1.28.16, mypy-boto3-s3<2.0.0,>=1.26.58, mypy-boto3-ses<2.0.0,>=1.34.141, mypy-boto3-sts<2.0.0,>=1.26.58, networkx<4.0.0,>=3, nltk<4.0.0,>=3.8.1, numpy<2,>=1.21.5, opensearch-py[async]<3.0.0,>=2.6.0, orjson<3.10.0,>=3.9.15, pandas-stubs>=1.5.0.221010, pandas<2,>=1, pgvector<0.3.0,>=0.2.1, psycopg2-binary<3.0.0,>=2.9.3, py-healthcheck<2.0.0,>=1.10.1, pyarrow-hotfix<0.7.0,>=0.6, pyarrow>=9.0.0, pydantic-settings==2.2.1, pydantic==2.7.1, pydevd-pycharm~=243.22562.220, pyjwt<3.0.0,>=2.8.0, pytest<=8.3.2,>=7.2.1, python-arango==7.5.7, python-json-logger<3.0.0,>=2.0.4, python_dateutil<3.0.0,>=2.6, pyyaml<7.0.0,>=6, redis[hiredis]<4.7.0,>=4.6, requests<2.32,>=2.31.0, rich<13.0.0,>=12.6.0, six<2.0.0,>=1.16, sqlalchemy-stubs<0.4.0,>=0.3, tenacity>=8.2, testcontainers<5.0.0,>=4.10.0, types-bleach<7.0.0,>=6.0.0.3, types-cachetools<6.0.0,>=5.3.0.7, types-python-dateutil==2.8.14, types-pytz<2023.0.0,>=2022.5.0.0, types-pyyaml<7.0.0,>=6, types-redis<5.0.0,>=4.6.0.5, types-requests<3.0.0,>=2.31.0.0, types-six<2.0.0,>=1.16.21, typing-extensions<5.0.0,>=4, unidecode<2.0.0,>=1.3.6, urllib3<2.0.0,>=1.26.9, werkzeug==2.2.3' failed with exit code 1.
   stdout:
   
   stderr:
   No pre-built wheel was available for thrift 0.16.0.
   Successfully built the wheel thrift-0.16.0-cp311-cp311-macosx_11_0_arm64.whl from the sdist thrift-0.16.0.tar.gz but it is not compatible with the requested foreign target complete platform cp39-cp39-manylinux_2_36_x86_64.
   You'll need to build a wheel from thrift-0.16.0.tar.gz on the foreign target platform and make it available to Pex via a `--find-links` repo or a custom `--index`.
   
   
   
   Use `--keep-sandboxes=on_failure` to preserve the process chroot for inspection.
   ```

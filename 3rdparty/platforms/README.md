# 3rd party platforms

This contains platforms used for PEX binaries so we can build for multiple platforms, i.e. `linux/amd64`, `linux/arm64`

## Create Platform Target(s)

In this example I am creating targets for 3.9 bookworm

1. Generate JSON files

   ```sh
   docker run -it --platform linux/amd64 public.ecr.aws/docker/library/python:3.9-slim-bookworm bash -c 'pip install pex; pex3 interpreter inspect --markers --tags' | grep platform_python_implementation | jq . >| docker_python_3_9_bookworm_amd64.json
   ```

   ```sh
   docker run -it --platform linux/arm64 public.ecr.aws/docker/library/python:3.9-slim-bookworm bash -c 'pip install pex; pex3 interpreter inspect --markers --tags' | grep platform_python_implementation | jq . >| docker_python_3_9_bookworm_arm64.json
   ```

2. Create new files target

   ```text
   files(
       name="docker_python_3_9_bookworm",
       sources=["docker_python_3_9_bookworm_*.json"],
   )
   ```

3. Reference target in `pex_binary`'s `complete_platforms` argument

   ```text
   pex_binary(
       name="pex_binary",
       complete_platforms=[
           "3rdparty/platforms:docker_python_3_9_bookworm",
       ],
   )
   ```

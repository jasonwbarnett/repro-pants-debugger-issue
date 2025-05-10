python_sources(
    dependencies=["//3rdparty/python:python-default"]
)

pex_binary(
    name="pex_binary",
    include_tools=True,
    venv_hermetic_scripts=False,
    complete_platforms=[
        f"3rdparty/platforms:docker_python_3_9_bookworm_amd64",
    ],
    dependencies=["//src/webapp:webapp"],
    # Optimal settings for Docker builds
    layout="packed",
    execution_mode="venv",
)

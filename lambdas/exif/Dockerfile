FROM public.ecr.aws/lambda/python:3.13

# install uv
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

COPY pyproject.toml ${LAMBDA_TASK_ROOT}/

RUN uv sync

COPY handler.py ${LAMBDA_TASK_ROOT}/

RUN uv sync --locked --no-install-project --no-editable

CMD ["handler.exif_handler"]

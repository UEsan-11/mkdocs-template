FROM python:3.12-slim
WORKDIR /root/mkdocs
RUN pip install --no-cache-dir mkdocs mkdocs-material mkdocs-awesome-pages-plugin mkdocs-mermaid2-plugin
EXPOSE 8000
CMD ["mkdocs", "serve", "-a", "0.0.0.0:8000"]

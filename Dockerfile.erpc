# Base image
FROM ghcr.io/erpc/erpc:latest

# Install gomplate for advanced templating
RUN apk add --no-cache curl && \
    curl -L https://github.com/hairyhenderson/gomplate/releases/download/v3.11.3/gomplate_linux-amd64 -o /usr/local/bin/gomplate && \
    chmod +x /usr/local/bin/gomplate

# Set environment variables (these can be empty or set by your CI/CD environment)
ENV ALCHEMY_API_KEY=""
ENV BLASTAPI_API_KEY=""
ENV DRPC_API_KEY=""

# Copy the template config
COPY erpc.yaml /root/erpc.yaml.template

# Generate the final config file at runtime
CMD gomplate -f /root/erpc.yaml.template -o /root/erpc.yaml && ./erpc-server
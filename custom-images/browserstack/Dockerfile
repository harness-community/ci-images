# Stage 1: Pull BrowserStack Local
FROM browserstack/local:latest as browserstack

# Stage 2: Final Image with Node.js & BrowserStack Local
FROM harnesscommunity/ci-base-image:latest

LABEL maintainer="Harness Community Engineering <community-engineering@harness.io>"

# Define versions
ENV NODE_VERSION=20.11.1
ENV PATH=/usr/local/bin:$PATH

# Copy only the required BrowserStack Local binary
COPY --from=browserstack /BrowserStackLocal /BrowserStackLocal

# Install Node.js (Latest LTS Version)
RUN apt-get update && \
    apt-get install -y --no-install-recommends curl ca-certificates && \
    curl -fsSL "https://deb.nodesource.com/setup_20.x" | bash - && \
    apt-get install -y nodejs && \
    npm install -g npm@latest && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Set default entrypoint to BrowserStack Local
ENTRYPOINT ["/BrowserStackLocal"]
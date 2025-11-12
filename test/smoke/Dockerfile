# FROM alpine

# RUN apk add curl

# COPY smoke-test.sh smoke-test.sh

# CMD ["sh", "smoke-test.sh", "http://app:3000"]

# Start from the Alpine image
FROM alpine

# Install curl
RUN apk add --no-cache curl

# Copy the smoke test script into the container
COPY smoke-test.sh /smoke-test.sh

# Create a non-root user (e.g., "appuser") and set permissions on the smoke test script
RUN adduser -D -g '' appuser && \
    chown appuser:appuser /smoke-test.sh

# Switch to the non-root user
USER appuser

# Define the command to run the smoke test script
CMD ["sh", "/smoke-test.sh", "http://app:3000"]

# Use a base image with CentOS
FROM centos:latest

# Set environment variables
ENV SETUP_PATH /www
ENV PANEL_PORT 8888
ENV SET_SSL true

# Copy the installation script to the container
COPY install.sh /tmp/install.sh

# Run necessary commands to set up aaPanel
RUN set -ex \
    && chmod +x /tmp/install.sh \
    && /tmp/install.sh \
    && rm -f /tmp/install.sh

# Expose the panel port
EXPOSE $PANEL_PORT

# Command to start the panel
CMD ["sh", "-c", "/www/server/panel/start.sh"]

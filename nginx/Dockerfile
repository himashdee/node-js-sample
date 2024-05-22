FROM nginx

# Create a non-root user
RUN adduser \
    --disabled-password \
    --gecos "" \
    --uid 10014 \
    "choreo"

# Create necessary directories with appropriate permissions
RUN mkdir -p /var/cache/nginx/client_temp && \
    chown -R choreo /var/cache/nginx && \
    touch /var/run/nginx.pid && \
    chown -R choreo /var/run/nginx.pid

EXPOSE 80

# Switch to the non-root "choreo" user and execute the script and start nginx
USER 10014
CMD /usr/sbin/nginx -g 'daemon off;'

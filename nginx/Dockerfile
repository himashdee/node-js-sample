FROM nginx

# Create a non-root user "app"
RUN addgroup -S choreo && adduser -S choreo -G choreo

# Create necessary directories with appropriate permissions
RUN mkdir -p /var/cache/nginx/client_temp && \
    chown -R choreo:choreo /var/cache/nginx && \
    touch /var/run/nginx.pid && \
    chown -R choreo:choreo /var/run/nginx.pid

EXPOSE 80

# Switch to the non-root "choreo" user and execute the script and start nginx
USER choreo
CMD /usr/sbin/nginx -g 'daemon off;'

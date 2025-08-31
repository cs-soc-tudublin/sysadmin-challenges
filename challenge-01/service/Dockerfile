FROM nginx:alpine

# Copy the static & index.html files to the nginx html directory
COPY ./static /usr/share/nginx/html/static
COPY ./index.html /usr/share/nginx/html/index.html

# Expose port 80
EXPOSE 80
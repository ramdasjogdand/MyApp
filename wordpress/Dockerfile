
# Stage 1: Build WordPress
FROM wordpress:latest AS builder

# Set the working directory
WORKDIR /var/www/html

# Remove the default WordPress themes and plugins
RUN rm -rf wp-content/themes/* wp-content/plugins/*

# Copy custom themes and plugins
COPY wp-content/themes /var/www/html/wp-content/themes
COPY wp-content/plugins /var/www/html/wp-content/plugins

# Stage 2: Final Image
FROM wordpress:latest

# Copy files from the builder stage
COPY --from=builder /var/www/html/wp-content/themes /var/www/html/wp-content/themes
COPY --from=builder /var/www/html/wp-content/plugins /var/www/html/wp-content/plugins

# Expose port 80
EXPOSE 80

# Command to run WordPress
CMD ["apache2-foreground"]

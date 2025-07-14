FROM serversideup/php:8.3-fpm-nginx

USER root

# Install PHP extensions
RUN install-php-extensions intl bcmath exif excimer

# Install Puppeteer dependencies
RUN apt-get update && \
    apt-get install -yq \
        gconf-service libasound2 libatk1.0-0 libc6 libcairo2 \
        libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgbm1 libgcc1 libgconf-2-4 \
        libgdk-pixbuf2.0-0 libglib2.0-0 libgtk-3-0 libnspr4 libpango-1.0-0 \
        libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 \
        libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 \
        libxss1 libxtst6 ca-certificates fonts-liberation libnss3 lsb-release  \
        xdg-utils wget && \
    rm -rf /var/lib/apt/lists/*

# Install Node.js
RUN curl -fsSL https://deb.nodesource.com/setup_22.x | bash - \
    apt-get install -y nodejs

WORKDIR /var/www/html

USER www-data

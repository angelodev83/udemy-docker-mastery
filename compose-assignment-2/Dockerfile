
FROM drupal:9
# install git -y automatically say yes
#when we run apt-get ,it creates a cache, we want to
#delete it to save memory. type clean up, not mandatory th
RUN apt-get update && apt-get install -y git \
    && rm -rf /var/lib/apt/lists/*

# directory where the actions or changes will take place
WORKDIR /var/www/html/themes

COPY index.html index.html

# I don't have to specify EXPOSE or CMD because they're in my FROM

# gets latest commit not the entire repository:
# these files get downloaded to root 
# apache server expects files to be www datauser so change permissions
RUN git clone --branch 8.x-4.x --single-branch --depth 1 https://git.drupalcode.org/project/bootstrap.git`\
    && chown -R www-data:www-data bootstrap

#GET BACK TO initial working directory
WORKDIR /var/www/html

# no need to install CMD theyre specified in the from image.

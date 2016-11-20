
# Wordpress Stateless Setup

Used to initialize a fresh Database and generate a wp-config.php file.

- Adjust settings in wp-cli.yml
- Run Container with mapped output folder to save wp-config.php
- Execute setup.sh via CMD parameter to the docker container

> docker run --name wp_stateless_setup --rm  --interactive \
-v $(pwd)/output:/var/config \
-v $(pwd)/wp-cli.yml:/var/www/html/wp-cli.yml \
-v $(pwd)/setup.sh:/var/www/html/setup.sh \
wordpress-stateless:cli /var/www/html/setup.sh
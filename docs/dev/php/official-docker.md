# The Official PHP Docker Image

The [official PHP Docker image][1] is a good starting place for many PHP projects.  It's a rock-solid implementation of PHP with close attention paid to best practices for PHP.  The downside of this image is that it is *not* covered in the main different articles and blog posts on the Internet that cover how to configure PHP.  This page is where I try to fill in some of the gaps.

## Location of Installed Resources

### Configuration Files

While configuring your application you may need to update the default configuration settings for the image.  The table below lists the locations of some of these files.

| Configuration             | Location                              | Image Variant |
|---------------------------|---------------------------------------|---------------|
| PEAR                      | `/usr/local/etc/pear.conf`            | All           |
| PHP-FPM Enabled           | `/usr/local/etc/php-fpm.conf`         | FPM           |
| PHP-FPM Enabled Site      | `/usr/local/etc/php-fpm.d/www.conf`   | FPM           | 

### Key Binaries

Below are some of the key binary files that you may need to know about and whether or not they are on the [`PATH`][2].

| Binaries                  | Location                       | Image Variant | On `PATH` ? |
|---------------------------|--------------------------------|---------------|-------------|
| FPM Binary                | `/usr/local/sbin/php-fpm`      | FPM           | Yes         |
| [PHPize][3]                    | `/usr/local/bin/phpize`        | All           | Yes         |



[1]: https://hub.docker.com/_/php
[2]: http://www.linfo.org/path_env_var.html
[3]: https://www.php.net/manual/en/install.pecl.phpize.php
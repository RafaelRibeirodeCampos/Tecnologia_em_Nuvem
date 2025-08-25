# Usa a imagem oficial do PHP com Apache
FROM php:8.2-apache

# Porta usada pelo Render
ENV PORT=8080

# Ativa o mod_rewrite para URLs amigáveis
RUN a2enmod rewrite

# Copia o código da aplicação
COPY . /var/www/html/

# Corrige permissões
RUN chown -R www-data:www-data /var/www/html && chmod -R 755 /var/www/html

# Permite acesso ao diretório
RUN echo '<Directory /var/www/html>' >> /etc/apache2/apache2.conf && \
    echo '  Options Indexes FollowSymLinks' >> /etc/apache2/apache2.conf && \
    echo '  AllowOverride All' >> /etc/apache2/apache2.conf && \
    echo '<Directory>' >> /etc/apache2/apache2.conf && \

FROM surnet/alpine-wkhtmltopdf:3.16.2-0.12.6-full as wkhtmltopdf_image
FROM degobbis/php80-fpm-alpine:latest

RUN apk update;

RUN apk add  --no-cache \
    bash \
    openssh-client \
    ;

RUN apk add  --no-cache \
	libstdc++ \
	libx11 \
	libxrender \
	libxext \
	libssl1.1 \
	fontconfig \
	freetype \
	ttf-dejavu \
	ttf-droid \
	ttf-freefont \
	ttf-liberation \
    ;

# wkhtmltopdf copy bins from ext image
COPY --from=wkhtmltopdf_image /bin/wkhtmltopdf /bin/libwkhtmltox.so /bin/

RUN ln -s /bin/wkhtmltopdf /usr/local/bin/wkhtmltopdf;
RUN ln -s /bin/wkhtmltopdf /usr/bin/wkhtmltopdf;
RUN chmod +x /usr/local/bin/wkhtmltopdf;
# makefile 

NAME		= draft-aumasson-blake3-00

$(NAME).pdf:	$(NAME).ps
		ps2pdf -sPAPERSIZE=a4 $(NAME).ps $(NAME).pdf

$(NAME).ps:	$(NAME).txt
		enscript -C -b '%D %C|$$n|$$%/$$=' \
			$(NAME).txt -o $(NAME).ps

$(NAME).txt:	$(NAME).xml
		xml2rfc $(NAME).xml -o $(NAME).txt

dist:		clean
		cd ..; tar cfvJ rfc/$(NAME)-`date "+%Y%m%d%H%M00"`.txz rfc/*

clean:
		rm -f $(NAME)-*.txz $(NAME).txt $(NAME).ps $(NAME).pdf

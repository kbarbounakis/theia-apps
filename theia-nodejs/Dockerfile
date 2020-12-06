FROM theiaide/theia:latest

# switch user to root
USER root
# update packages
RUN apk update
RUN apk add --no-cache sudo
RUN echo '%theia ALL=(ALL) NOPASSWD: ALL' > /etc/sudoers
# See https://github.com/sudo-project/sudo/issues/42
RUN echo "Set disable_coredump false" >> /etc/sudo.conf
# See https://wiki.alpinelinux.org/wiki/Setting_up_a_new_user#addgroup
RUN addgroup theia wheel
# add extra packages
RUN apk add g++ gcc make python
# upgrade terminal
RUN echo 'export PS1="\w \\$ "' >> /home/theia/.bashrc
# switch user to theia
USER theia

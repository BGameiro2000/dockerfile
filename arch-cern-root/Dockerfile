# Use archlinux:latest as parent image
FROM archlinux:latest

# Set maintainer
LABEL maintainer='BGameiro <projects+docker@bgameiro.me>'

# Update mirrors and packages. Install root.
RUN pacman --noconfirm -Syyu jupyter root

# Expose port and path
EXPOSE 8888
VOLUME /appdata

# Run root
CMD cp -R -n /usr/share/jupyter/* /appdata && root --notebook --ip=* --port=8888 --no-browser --notebook-dir=/appdata --allow-root

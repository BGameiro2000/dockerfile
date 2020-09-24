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
CMD mkdir /appdata/cern-root && mkdir /appdata/cern-root && cp -R -n /usr/share/jupyter/* /appdata/jupyter && cp -R -n /usr/share/cern-root/* /appdata/cern-root && root --notebook --ip=* --port=8888 --no-browser --notebook-dir=/opt/app/data --allow-root --app-dir=/appdata/jupyter
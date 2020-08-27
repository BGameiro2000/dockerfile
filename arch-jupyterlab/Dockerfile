# Use archlinux:latest as parent image
FROM archlinux:latest

# Set maintainer
LABEL maintainer='BGameiro <projects+docker@bgameiro.me>'

# Update mirrors and packages
RUN pacman --noconfirm -Syyu jupyterlab

# Expose port and path
EXPOSE 8888
VOLUME /appdata

# Add packages and functionalities
# ENV pkgs=PACKAGES
# CMD pacman --noconfirm -S 

# Run JupyterLab
CMD cp -R -n /usr/share/jupyter/* /appdata && jupyter lab --ip=* --port=8888 --no-browser --notebook-dir=/opt/app/data --allow-root --config-dir=/appdata || jupyter lab --ip=* --port=8888 --no-browser --notebook-dir=/opt/app/data --allow-root --config-dir=/appdata --generate-config
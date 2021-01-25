# Use archlinux:latest as parent image
FROM archlinux:latest

# Set maintainer
LABEL maintainer='BGameiro <projects+docker@bgameiro.me>'

# Update mirrors and packages. Install jupyterlab
RUN pacman --noconfirm -Syyu python-pip nodejs
RUN pacman --noconfirm -U https://archive.archlinux.org/packages/j/jupyterlab_server/jupyterlab_server-1.2.0-3-any.pkg.tar.zst.sig
RUN pacman --noconfirm -U https://archive.archlinux.org/packages/j/jupyterlab/jupyterlab-2.2.9-2-any.pkg.tar.zst

# Build the lab
RUN jupyter lab build --minimize=False

# Expose port and path
EXPOSE 8888
VOLUME /appdata

# Add packages and functionalities
# ENV pkgs=PACKAGES
# CMD pacman --noconfirm -S 

# Run JupyterLab
CMD cp -R -n /usr/share/jupyter/* /appdata && jupyter lab --ip=* --port=8888 --no-browser --notebook-dir=/opt/app/data --allow-root --app-dir=/appdata/lab

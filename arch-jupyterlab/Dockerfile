# Use archlinux:latest as parent image
FROM archlinux:latest

# Set maintainer
LABEL maintainer='BGameiro <projects+docker@bgameiro.me>'

# Update mirrors and packages
RUN pacman --noconfirm -Syyu

# Expose port and path
EXPOSE 8888
RUN mkdir -p /opt/app/data

# Add packages and functionalities
ENV pkgs=PACKAGES
CMD pacman --noconfirm -S jupyterlab pkgs

# Run JupyterLab
CMD jupyter lab --ip=* --port=8888 --no-browser --notebook-dir=/opt/app/data --allow-root
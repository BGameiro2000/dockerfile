# Use archlinux:latest as parent image
FROM archlinux:latest

# Set maintainer
LABEL maintainer='BGameiro <projects+docker@bgameiro.me>'

# Update and install jupyterlab
RUN pacman --noconfirm -Syyu jupyterlab

# Expose port and path
EXPOSE 8888
RUN mkdir -p /opt/app/data

# TODO: python-ipykernel evcxr_jupyter jupyter-octave_kernel

# Run JupyterLab
CMD jupyter lab --ip=* --port=8888 --no-browser --notebook-dir=/opt/app/data --allow-root
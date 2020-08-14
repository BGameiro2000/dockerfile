# Use archlinux:latest as parent image
FROM archlinux:latest

# Set maintainer
LABEL maintainer='BGameiro <projects+docker@bgameiro.me>'

# Update and install jupyterlab
RUN pacman --noconfirm -Syyu jupyterlab

# TODO: python-ipykernel evcxr_jupyter jupyter-octave_kernel
# Use archlinux:latest as parent image
FROM archlinux:latest

# Set maintainer
LABEL maintainer='BGameiro <projects+docker@bgameiro.me>'

# Temporary fix for 'failed to initialize alpm library (could not find or read directory: /var/lib/pacman/)'
RUN mkdir -p /var/lib/pacman/
# Update mirrors and packages. Install xpra, alacritty and openscad.
RUN pacman --noconfirm -Syyu xpra alacritty openscad

# Expose port and path
EXPOSE 8888
VOLUME /appdata

# Start xpra in screen 10 and bind to port 8888
CMD xpra start :10 --bind-tcp=0.0.0.0:8888

# Start alacritty and openscad in screen 10
CMD DISPLAY=:10 alacritty
CMD DISPLAY=:10 openscad

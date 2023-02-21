# Use archlinux:latest as parent image
FROM archlinux:latest

# Set maintainer
LABEL maintainer='BGameiro <projects+docker@bgameiro.me>'

# Update mirrors and packages. Install jupyterlab
RUN pacman --noconfirm -Syyu \
                              # Jupyter
                              jupyterlab \
                              python-ipykernel \
                              # PyData
                              python-scipy \
                              python-pandas \
                              python-numpy \
                              python-matplotlib \
                              python-scikit-learn \
                              python-pytorch \
                              python-dask \
                              python-xarray \
                              python-distributed \
                              # Python Physics
                              python-mplhep \
                              # Python helpers
                              python-pyarrow \
                              python-tqdm \
                              # ROOT
                              root \
                              python-uproot
                              
RUN pip install --user \
                              jupyterlab-visualpython \
                              dexplot

ENV JUPYTERLAB_DIR /appdata/lab

# Build the lab
RUN jupyter lab build --minimize=False

# Expose port and path
EXPOSE 8888
VOLUME /appdata

# Add packages and functionalities
# ENV pkgs=PACKAGES
# CMD pacman --noconfirm -S 

# Run JupyterLab
CMD cp -R -n /usr/share/jupyter/* /appdata && jupyter lab --ip=* --port=8888 --no-browser --notebook-dir=/opt/app/data --allow-root

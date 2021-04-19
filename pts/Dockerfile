# Use phoronix/pts:latest as parent image
FROM phoronix/pts:latest

# Set maintainer
LABEL maintainer='BGameiro <projects+docker@bgameiro.me>'

# Create alias
RUN alias pts=”/phoronix-test-suite/phoronix-test-suite”

# Install tests
RUN /phoronix-test-suite/phoronix-test-suite install server network server-memory server-cpu-tests workstation cryptography disk
RUN /phoronix-test-suite/phoronix-test-suite install scientific-computing hpc linear-algebra machine-learning mpi quantum-mechanics

# Create alias for bench
RUN alias bench=”/phoronix-test-suite/phoronix-test-suite default-benchmark”
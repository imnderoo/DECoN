#################################################################
# Dockerfile # # Version: 0.1
# Software: DECoN V1.0.2
# Description: DECoN Detection of Exon Copy Number variants
# Website: http://www.thetgmi.org/tgmi-news/detecting-tricky-gene-mutations/
# Tags: None, for the moment
# Base Image: r-base:3.1.2
#################################################################

FROM r-base:3.1.2

ENTRYPOINT ["/bin/bash"]

### Adding user decon
RUN useradd -ms /bin/bash decon

### Adding Certificates for wget tu download from git
RUN apt-get update && apt-get install -y ca-certificates && rm -rf /var/lib/apt/lists/*

### Running Container as decon and install decon from git
USER decon
WORKDIR /home/decon/
RUN wget https://github.com/RahmanTeam/DECoN/archive/v1.0.2.tar.gz
RUN tar -xzvf v1.0.2.tar.gz
Run rm v1.0.2.tar.gz
WORKDIR /home/decon/DECoN-1.0.2/Linux/

### Starting setup
RUN mkdir /home/decon/DECoN-1.0.2/Linux/packrat/src/VGAM/
RUN wget https://cran.r-project.org/src/contrib/Archive/VGAM/VGAM_0.9-8.tar.gz -O /home/decon/DECoN-1.0.2/Linux/packrat/src/VGAM/VGAM_0.9-8.tar.gz
RUN ./setup.sh

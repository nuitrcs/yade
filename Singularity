Bootstrap: docker

# Choose Linux distribution to bootstrap 
From: ubuntu:16.04 # (ubuntu Xenial)
# From: ubuntu:14.04 # (ubuntu Trusty)
# From: ubuntu:18.04 # (ubuntu Bionic Beaver)
# From: fedora:latest
# From: alpine:latest

%environment

    # Set system locale
    export LC_ALL=C

%post

    # ------------------------------------------------ #
    #           Package installation section 	 	   #
    #												   #
    # Use for installing packages "system-wide" in 	   #
    # the container. Linux uses `apt-get` to install.  #
    #												   #
    # NOTE: Alpine Linux uses the `apk` tool, NOT 	   #
    # `apt-get` (https://bit.ly/2rfQHzp)			   #
    #												   #
    # NOTE: Fedora uses the `yum` tool, NOT 	   	   #
    # `apt-get` (https://bit.ly/2vnkRUu)			   #
    # ------------------------------------------------ #

    # UBUNTU: update apt-get's pacakge list and upgrade will install newer
    # versions of the pacakges already installed.
    apt-get -y update && apt-get -y upgrade
    apt-get -y --allow-unauthenticated install \
    apt-utils \
	autoconf \
	automake \
	build-essential \
	cmake \
	curl \
	git \
	gfortran \
	libtool \
	libssl-dev \
	libffi-dev \
	libxslt1-dev \
	libxml2-dev \
	pkg-config \
	unzip \
	vim \
	wget \
	zip \
	yade

	# (other packages you may find useful)
	#autoconf \
	#automake \
	#gfortran \
	#python-dev \
	#python-pip \
	#python-tk \
	#python-wheel \
	#python3-dev \
	#python3-pip \
	#python3-wheel \
	#zlib1g-dev


	# ------------------------------------------------ #
    #               		ETC...					   #
    # 		Set default OS + Singularity settings	   #
    # ------------------------------------------------ #

	# (Mount /software dir bind point for Quest)
    mkdir /software

	# (Set bash Bourne shell as default shell)
	SHELL=/bin/bash


	# ------------------------------------------------ #
    #            Install extraneous software		   #
    # ------------------------------------------------ #

	# (Install Miniconda python package manager 2 or 3)
	#MINICONDA_VERSION='3' # change to '2' for Python 2.7 Miniconda
	#wget -P /opt 'https://repo.continuum.io/miniconda/Miniconda'$MINICONDA_VERSION'-latest-Linux-x86_64.sh'
	#bash /opt/Miniconda*.sh -b -p /opt/anaconda
	#rm /opt/Miniconda*.sh
	#echo 'export PATH="/opt/anaconda/bin:$PATH"' >> $SINGULARITY_ENVIRONMENT

%test
	
	# ------------------------------------------------ #
    #              Tests: must pass on build 		   #
    # You may not be able to run these as a non-sudo   #
    # user when deployed on Quest.					   #
    # ------------------------------------------------ #

    # If os-release file exists (Ubuntu distros), display it.
	if [ -f /usr/lib/os-release ]; then
    	cat /usr/lib/os-release
    fi

%files

%runscript

%environment


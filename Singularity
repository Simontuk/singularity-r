BootStrap: docker
From: centos:latest
IncludeCmd: yes


%labels
  Maintainer Simon Steiger
  R_Version 3.6.1

%apprun R
  exec R "${@}"

%apprun Rscript
  exec Rscript "${@}"

%runscript
  exec R "${@}"

%post
  # Software versions
  export R_VERSION=3.6.1
  
  # Configure default locale
  localedef -c -f UTF-8 -i en_US en_US.UTF-8
  export LC_ALL=en_US.UTF-8
  export LANG=en_US.UTF-8
  echo "LC_ALL=en_US.UTF-8" >> /etc/environment
  echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen
  echo "LANG=en_US.UTF-8" > /etc/locale.conf
  

# Get dependencies
  yum install -y epel-release
  yum update -y

  yum groupinstall -y "Development Tools"
  yum install -y libcurl-devel openssl-devel libxml2-devel hdf5-devel libssh2-devel
  yum install -y libpng-devel libjpeg-turbo-devel cairo-devel

  yum install -y R

  # Add a default CRAN mirror
  echo "options(repos = c(CRAN = 'https://cran.rstudio.com/'), download.file.method = 'libcurl')" >> /usr/lib64/R/etc/Rprofile.site

  # Add a directory for host R libraries
  mkdir -p /library
  echo "R_LIBS_SITE=/library:\${R_LIBS_SITE}" >> /usr/lib64/R/etc/Renviron.site


  # Clean up
  yum clean all

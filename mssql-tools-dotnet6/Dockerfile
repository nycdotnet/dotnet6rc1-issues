FROM mcr.microsoft.com/dotnet/sdk:5.0 AS dev

RUN apt-get update && \
    apt-get install -y gnupg2 apt-transport-https debconf-utils

RUN wget -qO- https://packages.microsoft.com/keys/microsoft.asc | apt-key add - && \
  echo "deb [arch=amd64] https://packages.microsoft.com/debian/10/prod buster main" | tee /etc/apt/sources.list.d/msprod.list

RUN apt-get update && \
  ACCEPT_EULA=Y apt-get install -y mssql-tools

CMD dotnet --version && /opt/mssql-tools/bin/bcp -v
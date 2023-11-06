FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build01
WORKDIR /app
COPY . .
RUN dotnet restore
RUN dotnet publish -c Release -o out

FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /target
COPY --from=build01 /app/out .
ENTRYPOINT ["dotnet", "hello-api.dll"]

#docker image build -t api:1.0 .
#docker container run -p 5001:5000 api:1.0
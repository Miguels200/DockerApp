FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR webDockerPrueba

EXPOSE 80
EXPOSE 8080

#COPY PROJECT FILES
COPY ./*.csproj ./

RUN dotnet restore

#COPY EVERYHING ELSE
COPY . . 
RUN dotnet publish -c Realese -o out


#BUILD IMAGES 
FROM mcr.microsoft.com/dotnet/sdk:8.0 
WORKDIR webDockerPrueba
COPY --from=build /webDockerPrueba/out .
ENTRYPOINT ["dotnet","DockerApp.dll"]
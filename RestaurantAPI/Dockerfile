#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

#Depending on the operating system of the host machines(s) that will build or run the containers, the image specified in the FROM statement may need to be changed.
#For more information, please see https://aka.ms/containercompat
#
#FROM mcr.microsoft.com/dotnet/aspnet:5.0 AS base
#
#
#FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
#WORKDIR /src
#COPY ["RestaurantAPI/RestaurantAPI.csproj", "RestaurantAPI/"]
#RUN dotnet restore "RestaurantAPI/RestaurantAPI.csproj"
#COPY . .
#WORKDIR "/src/RestaurantAPI"
#RUN dotnet build "RestaurantAPI.csproj" -c Release -o /app/build
#
#FROM build AS publish
#RUN dotnet publish "RestaurantAPI.csproj" -c Release -o /app/publish
#
#FROM base AS final
#WORKDIR /app
#COPY --from=publish /app/publish .
#ENTRYPOINT ["dotnet", "RestaurantAPI.dll"]
FROM mcr.microsoft.com/dotnet/aspnet:5.0 AS base






 

 

FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /src
COPY RestaurantAPI.csproj .
RUN dotnet restore
COPY . .
RUN dotnet publish -c release -o /app

 

FROM mcr.microsoft.com/dotnet/aspnet:5.0
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "RestaurantAPI.dll"]
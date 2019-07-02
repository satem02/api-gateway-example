FROM microsoft/dotnet:2.2-aspnetcore-runtime AS base
WORKDIR /app
EXPOSE 80

FROM microsoft/dotnet:2.2-sdk AS build
WORKDIR /src
COPY ["FirstApi/FirstApi.csproj", "FirstApi/"]
RUN dotnet restore "FirstApi/FirstApi.csproj"
COPY . .
WORKDIR "/src/FirstApi"
RUN dotnet build "FirstApi.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "FirstApi.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "FirstApi.dll"]

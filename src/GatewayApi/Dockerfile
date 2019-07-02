FROM microsoft/dotnet:2.2-aspnetcore-runtime AS base
WORKDIR /app
EXPOSE 80

FROM microsoft/dotnet:2.2-sdk AS build
WORKDIR /src
COPY ["GatewayApi/GatewayApi.csproj", "GatewayApi/"]
RUN dotnet restore "GatewayApi/GatewayApi.csproj"
COPY . .
WORKDIR "/src/GatewayApi"
RUN dotnet build "GatewayApi.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "GatewayApi.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "GatewayApi.dll"]

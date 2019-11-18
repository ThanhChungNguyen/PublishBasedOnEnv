# PublishBasedOnEnv
For console app:
  In main function, add below code to read appsetting base on env
  
                  var environmentName = Environment.GetEnvironmentVariable("ASPNETCORE_ENVIRONMENT");
                var builder = new ConfigurationBuilder()
                    .SetBasePath(Directory.GetCurrentDirectory())
                    .AddJsonFile("appsettings.json", optional: true, reloadOnChange: true)
                    .AddJsonFile("appsettings." + environmentName + ".json", optional: true, reloadOnChange: true);
                var config =  builder.Build();

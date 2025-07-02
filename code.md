<picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github.com/jghosh2020/jghosh2020.github.io/blob/main/images/Azure_OpenAI.jpg">
</picture>

```
using Microsoft.Extensions.Configuration;

namespace gpt4_lab
{
    public class Program
    {
        static async Task Main(string[] args)
        {
            var config = new ConfigurationBuilder()
                .AddJsonFile("appsettings.json")
                .Build();

            var service = new AzureOpenAIService(config);

            while (true)
            {
                Console.Write("Say Something:");
                var input = Console.ReadLine();

                if (input.ToLower() == "exit") break;

                var output = await service.GetCompletionAsync(input);
                Console.WriteLine("GPT-4: " + output);

            }
        }

    }
}

```

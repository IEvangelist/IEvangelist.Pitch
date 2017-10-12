Slide 1
---
Slide 2
---
Before
```csharp
using System.Collections.Concurrent;

namespace IEvangelist.Csharp.Seven
{
    class Program
    {
        public static void Main() { }
    }

    public static class ConcurrentExtensions
    {
        public static T TryPeekOrDefault<T>(
            this ConcurrentQueue<T> queue)
        {
            if (queue?.TryPeek(out T result) ?? false)
            {
                return result;
            }
            
            return default;
        }            
    }
}
```
+++
After
```csharp
using System.Collections.Concurrent;

namespace IEvangelist.Csharp.Seven
{
    class Program
    {
        public static void Main() { }
    }

    public static class ConcurrentExtensions
    {
        public static T TryPeekOrDefault<T>(
            this ConcurrentQueue<T> queue) => 
            (queue?.TryPeek(out T result) ?? false) ? result : default;
    }
}
```
---

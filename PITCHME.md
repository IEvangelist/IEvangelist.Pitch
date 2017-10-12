Slide 1
---
Slide 2
---
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
        public static T TryPeekOrDefault<T>(this ConcurrentQueue<T> queue)
            => (queue?.TryPeek(out T result) ?? false) ? result : default;
    }
}
```

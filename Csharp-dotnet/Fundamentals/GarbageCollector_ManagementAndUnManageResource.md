## How do you handle unmanage Resource ?

“In .NET, the GC only manages managed memory. Anything external—file handles, sockets, native memory, window handles—must be released manually.
The recommended approach is the Dispose pattern:

Implement IDisposable

Implement a protected Dispose(bool disposing) method

When disposing == true, free managed + unmanaged resources

When disposing == false, free only unmanaged resources

Add a finalizer only if you directly hold unmanaged resources

Call GC.SuppressFinalize(this) inside Dispose() to prevent double cleanup

Prefer SafeHandle instead of raw IntPtr because it handles finalization safely

This pattern ensures deterministic cleanup and prevents resource leaks even if the consumer forgets to call Dispose.”

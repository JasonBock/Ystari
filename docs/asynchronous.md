# Asynchronous

Every operation in Ystari would be asynchronous only. That is, the `Create`, `Fetch`, `Save` (encompassing `Insert`, `Update` and `Delete`), and `Execute` (on commands) would only have asynchronous definitions. Currently in CSLA there are some issues with having both synchronous and asynchronous versions of these operations (see [this](https://github.com/MarimerLLC/cslaforum/issues/112) for details). This would eliminate the issue and enforce an approach where these operations should typically be executed in an asynchronous fashion. If the developer chooses not to make the call asynchornously, they can always return `Task.CompletedTask`.
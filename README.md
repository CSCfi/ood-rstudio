# Batch Connect - Example RStudio Server

Batch Connect app that launches an RStudio server within a
batch job.

Direct authentication is broken for versions `4.0.4,4.0.5` + 
you get an external server error when connecting 
to the `4.0.5` version using the `auth-do-sign-in` url ending.
This then requires manually editing the url (make it end in `<port>/`) and reloading
after manually inputting the password and being redirected to some internal error page.

This can be fixed if we can dynamically drop the `auth-do-sign-in` depending on the version. The we could just insert the password normally. For completely auto login,
something needs to be fixed / changed for the newest versions rstudio.  
Solution for direct authentication that seems to work, may break in future versions: <https://discourse.osc.edu/t/rstudio-when-launched-without-singularity-is-having-strange-troubles-with-authentication/1213/48>

# API Limits

When pushing results set to LegiTest Online, the maximum request limit for the API is set to 20MB.

## On-Premise

The On-Premise version can have this restriction changed, although by default is set to 20MB to match the online version.
To change the limit, access the web.config file in the installation directory and make the following changes:

1) <system.web>
    <httpRuntime targetFramework="4.5" maxRequestLength="20480"/>  -- maxRequestLength given in KB


2) <system.webServer>
        <requestFiltering>
            <requestLimits maxAllowedContentLength="201971520"/> -- maxAllowedContentLength given in bytes
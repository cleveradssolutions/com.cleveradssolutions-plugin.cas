# cas.hideBanner()

> --------------------- ------------------------------------------------------------------------------------------
> __Type__              [Function][api.type.Function]
> __Return value__      none
> __Keywords__          ads, advertising, Clever Ads Solutions, CAS, hideBanner
> __See also__          [cas.showBanner()][plugin.cas.showBanner]
>						[cas.*][plugin.cas]
> --------------------- ------------------------------------------------------------------------------------------


## Overview

Hide a banner ad.

<div class="guide-notebox">
<div class="notebox-title">Note</div>

Once you initialize the plugin with [cas.init()][cas.cas.init], `CAS SDK` will automatically start loading ads. 

</div>


## Syntax

    cas.hideBanner()

## Example

``````lua
local cas = require( "plugin.cas" )

-- CAS listener function
local function adListener( event )

	if ( event.phase == "init" ) then  -- Successful initialization
		print( event.provider )
	end
end

-- Initialize the CAS plugin
cas.init( adListener, { managerId="YOUR_MANAGER_ID", testMode=true, banner=true, interstitial=false, rewarded=true, appReturn=false } )
-- Sometime later, show an ad
if ( cas.isAdReady( 0 ) ) then
	cas.showBanner()
end

-- Sometime later, show an ad
cas.hideBanner()
``````
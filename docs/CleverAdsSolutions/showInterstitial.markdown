# cas.showInterstitial()

> --------------------- ------------------------------------------------------------------------------------------
> __Type__              [Function][api.type.Function]
> __Return value__      none
> __Keywords__          ads, advertising, Clever Ads Solutions, CAS, showInterstitial
> __See also__          [cas.isInterstitialReady()][plugin.cas.isInterstitialReady]
>						[cas.*][plugin.cas]
> --------------------- ------------------------------------------------------------------------------------------


## Overview

Shows an interstitial ad.

<div class="guide-notebox">
<div class="notebox-title">Note</div>

Once you initialize the plugin with [cas.init()][cas.cas.init], `CAS SDK` will automatically start loading ads. 

</div>


## Syntax

    cas.showInterstitial()

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
cas.init( adListener, { managerId="YOUR_MANAGER_ID", testMode=true, banner=false, interstitial=true, rewarded=true, appReturn=false } )

-- Sometime later, show an ad
if ( cas.isInterstitialReady() ) then
	cas.showInterstitial()
end
``````
---
title: SMB disaster recovery with Double-Take DR
author: adamboeglin
ms.date: 12/09/2019
description: Small and medium businesses can inexpensively implement disaster recovery to the cloud by using a partner solution like Double-Take DR.
ms.custom: acom-architecture
---
# SMB disaster recovery with Double-Take DR

Small and medium businesses can inexpensively implement disaster recovery to the cloud by using a partner solution like Double-Take DR.

This solution is built on the Azure managed services: [Traffic Manager](/services/traffic-manager/), [VPN Gateway](/services/vpn-gateway/) and [Virtual Network](/services/virtual-network/). These services run in a high-availability environment, patched and supported, allowing you to focus on your solution instead of the environment they run in.


## Architecture

<svg class="architecture-diagram" aria-labelledby="disaster-recovery-smb-double-take-dr" height="443.187" viewbox="0 0 825.047 443.187" width="825.047" xmlns="https://www.w3.org/2000/svg"><title id="disaster-recovery-smb-double-take-dr">Recuperao aps desastre para PMEs com o Double-Take DR</title><desc>As pequenas e mdias empresas podem implementar a recuperao aps desastre de forma econmica na cloud com uma soluo de parceiro como o Double-Take DR.</desc><g><line fill="none" stroke="#b5b5b5" stroke-miterlimit="10" stroke-width="1.643" x1="183.888" x2="314.648" y1="33.71" y2="33.71"></line><polygon fill="#b5b5b5" points="313.449 37.805 320.542 33.71 313.449 29.614 313.449 37.805"></polygon></g><rect fill="#ededed" height="315" opacity="0.5" width="362" x="463.047" y="128.187"></rect><rect fill="#ededed" height="315" opacity="0.5" width="282" x="0.001" y="128.187"></rect><g><polyline fill="none" points="386.168 99.009 386.168 111.729 620.869 111.729 620.869 122.791" stroke="#b5b5b5" stroke-miterlimit="10" stroke-width="1.643"></polyline><polygon fill="#b5b5b5" points="616.774 121.592 620.869 128.685 624.965 121.592 616.774 121.592"></polygon></g><g><polyline fill="none" points="357.869 99.009 357.869 111.729 151.168 111.729 151.168 122.791" stroke="#b5b5b5" stroke-miterlimit="10" stroke-width="1.643"></polyline><polygon fill="#b5b5b5" points="147.073 121.592 151.168 128.685 155.264 121.592 147.073 121.592"></polygon></g><g><line fill="none" stroke="#b5b5b5" stroke-miterlimit="10" stroke-width="1.643" x1="410.519" x2="483.345" y1="239.781" y2="239.781"></line><polygon fill="#b5b5b5" points="482.147 243.877 489.239 239.781 482.147 235.686 482.147 243.877"></polygon></g><g><line fill="none" stroke="#b5b5b5" stroke-miterlimit="10" stroke-width="1.643" x1="219.126" x2="329.345" y1="239.781" y2="239.781"></line><polygon fill="#b5b5b5" points="328.147 243.877 335.239 239.781 328.147 235.686 328.147 243.877"></polygon></g><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(727.851 121.207)">Azure <tspan letter-spacing="-0.034em" x="33.691" y="0">F</tspan><tspan x="39.141" y="0">ailover Site</tspan></text><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(732.095 157.067)"><tspan letter-spacing="-0.029em">R</tspan><tspan x="6.826" y="0">ecovery VMs</tspan></text><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(0 121.207)">Primary Site (On-Premise)</text><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(210 105.207)">Before <tspan letter-spacing="-0.034em" x="37.676" y="0">F</tspan><tspan x="43.125" y="0">ailover</tspan></text><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(459.518 105.207)">After <tspan letter-spacing="-0.034em" x="29.297" y="0">F</tspan><tspan x="34.746" y="0">ailover</tspan></text><polyline fill="none" points="197.519 326.637 219.126 326.637 219.126 169.711 197.519 169.711" stroke="#b5b5b5" stroke-miterlimit="10" stroke-width="1.643"></polyline><line fill="none" stroke="#b5b5b5" stroke-miterlimit="10" stroke-width="1.643" x1="600.244" x2="564.131" y1="239.781" y2="239.781"></line><g><polyline fill="none" points="615.957 169.712 600.244 169.712 600.244 326.636 615.957 326.636" stroke="#b5b5b5" stroke-miterlimit="10" stroke-width="1.643"></polyline><polygon fill="#b5b5b5" points="614.759 165.616 621.852 169.712 614.759 173.807 614.759 165.616"></polygon><polygon fill="#b5b5b5" points="614.759 330.732 621.852 326.636 614.759 322.541 614.759 330.732"></polygon></g><g opacity="0.5"><g><polyline fill="none" points="812.737 392.187 812.737 395.187 809.737 395.187" stroke="#b5b5b5" stroke-miterlimit="10" stroke-width="1.643"></polyline><line fill="none" stroke="#b5b5b5" stroke-dasharray="6.159 6.159" stroke-miterlimit="10" stroke-width="1.643" x1="803.578" x2="584.921" y1="395.187" y2="395.187"></line><polyline fill="none" points="581.842 395.187 578.842 395.187 578.842 392.187" stroke="#b5b5b5" stroke-miterlimit="10" stroke-width="1.643"></polyline><line fill="none" stroke="#b5b5b5" stroke-dasharray="6.041 6.041" stroke-miterlimit="10" stroke-width="1.643" x1="578.842" x2="578.842" y1="386.146" y2="147.541"></line><polyline fill="none" points="578.842 144.52 578.842 141.52 581.842 141.52" stroke="#b5b5b5" stroke-miterlimit="10" stroke-width="1.643"></polyline><line fill="none" stroke="#b5b5b5" stroke-dasharray="6.159 6.159" stroke-miterlimit="10" stroke-width="1.643" x1="588.001" x2="806.657" y1="141.52" y2="141.52"></line><polyline fill="none" points="809.737 141.52 812.737 141.52 812.737 144.52" stroke="#b5b5b5" stroke-miterlimit="10" stroke-width="1.643"></polyline><line fill="none" stroke="#b5b5b5" stroke-dasharray="6.041 6.041" stroke-miterlimit="10" stroke-width="1.643" x1="812.737" x2="812.737" y1="150.561" y2="389.167"></line></g></g><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(744.757 272.644)">*VMs <tspan x="0" y="14.4">aren't </tspan><tspan x="0" y="28.8">created </tspan><tspan x="0" y="43.2">until </tspan><tspan x="0" y="57.6">failover </tspan><tspan x="0" y="72">occurs</tspan></text><g><g><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(136.325 215.479)">IIS VM</text><g><path d="M159.867,190.7H147.752c1.456,5.139-.5,5.876-9.066,5.876v2.691h29.13v-2.691c-8.566,0-9.407-.734-7.949-5.876" fill="#7a7a7a"></path><path d="M172.835,158.143H133.4a2.52,2.52,0,0,0-2.421,2.537v27.5A2.506,2.506,0,0,0,133.4,190.7h39.439a2.753,2.753,0,0,0,2.692-2.515v-27.5a2.763,2.763,0,0,0-2.692-2.537" fill="#a0a1a2"></path><path d="M172.862,158.146l-.028,0h-39.44a2.519,2.519,0,0,0-2.421,2.537v27.5a2.506,2.506,0,0,0,2.421,2.516h.938Z" fill="#fff" opacity="0.2" style="isolation: isolate"></path><polygon fill="#59b4d9" points="172.049 161.572 172.049 187.27 134.351 187.27 134.351 161.572 172.049 161.572"></polygon><polygon fill="#59b4d9" points="134.351 187.27 134.403 187.27 134.403 161.573 168.868 161.521 168.869 161.521 134.351 161.573 134.351 187.27"></polygon><rect fill="#a0a1a2" height="2.692" width="29.13" x="138.686" y="196.571"></rect><path d="M153.711,160.01a.632.632,0,1,1-.633-.633.633.633,0,0,1,.633.633" fill="#b8d432"></path><path d="M153.736,173.641a.248.248,0,0,1-.119-.034l-7.845-4.528a.241.241,0,0,1-.118-.206.238.238,0,0,1,.118-.2l7.8-4.5a.239.239,0,0,1,.234,0l7.847,4.53a.238.238,0,0,1,0,.41l-7.795,4.5a.24.24,0,0,1-.12.034" fill="#fff"></path><path d="M152.609,184.647a.224.224,0,0,1-.119-.032l-7.821-4.514a.232.232,0,0,1-.121-.206v-9.058a.241.241,0,0,1,.36-.206l7.821,4.512a.249.249,0,0,1,.116.208v9.058a.242.242,0,0,1-.116.206.25.25,0,0,1-.119.032" fill="#fff" opacity="0.7" style="isolation: isolate"></path><path d="M154.823,184.647a.256.256,0,0,1-.123-.032.241.241,0,0,1-.115-.206v-9a.246.246,0,0,1,.115-.206l7.821-4.512a.232.232,0,0,1,.235,0,.235.235,0,0,1,.12.2v9a.233.233,0,0,1-.12.206l-7.818,4.514a.211.211,0,0,1-.115.032" fill="#fff" opacity="0.4" style="isolation: isolate"></path></g></g><rect fill="#f0f" height="64.118" opacity="0" width="47.675" x="128.816" y="156.675"></rect></g><g><g><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(124.776 363.669)">SQL Server<tspan x="4.992" y="14.4">2016 VM</tspan></text><g><path d="M154.228,333.807H143.8c1.253,4.424-.43,5.058-7.8,5.058v2.316H161.07v-2.316c-7.373,0-8.1-.632-6.842-5.058" fill="#7a7a7a"></path><path d="M165.39,305.788H131.443a2.169,2.169,0,0,0-2.084,2.183v23.673a2.157,2.157,0,0,0,2.084,2.165H165.39a2.37,2.37,0,0,0,2.317-2.165V307.971a2.378,2.378,0,0,0-2.317-2.183" fill="#a0a1a2"></path><path d="M165.414,305.79l-.024,0H131.442a2.168,2.168,0,0,0-2.084,2.183v23.672a2.157,2.157,0,0,0,2.084,2.166h.808Z" fill="#fff" opacity="0.2" style="isolation: isolate"></path><polygon fill="#59b4d9" points="164.713 308.739 164.713 330.859 132.265 330.859 132.265 308.739 164.713 308.739"></polygon><polygon fill="#59b4d9" points="132.265 330.859 132.31 330.859 132.31 308.74 161.975 308.695 161.977 308.695 132.265 308.74 132.265 330.859"></polygon><rect fill="#a0a1a2" height="2.317" width="25.073" x="135.997" y="338.865"></rect><path d="M148.93,307.395a.544.544,0,1,1-.545-.545.545.545,0,0,1,.545.545" fill="#b8d432"></path><path d="M148.951,319.128a.213.213,0,0,1-.1-.029l-6.752-3.9a.208.208,0,0,1-.1-.177.2.2,0,0,1,.1-.176l6.712-3.872a.205.205,0,0,1,.2,0l6.754,3.9a.205.205,0,0,1,0,.353l-6.709,3.872a.207.207,0,0,1-.1.029" fill="#fff"></path><path d="M147.981,328.6a.193.193,0,0,1-.1-.028l-6.732-3.885a.2.2,0,0,1-.1-.177v-7.8a.207.207,0,0,1,.31-.177l6.731,3.884a.214.214,0,0,1,.1.179v7.8a.208.208,0,0,1-.1.177.215.215,0,0,1-.1.028" fill="#fff" opacity="0.7" style="isolation: isolate"></path><path d="M149.887,328.6a.22.22,0,0,1-.106-.028.208.208,0,0,1-.1-.177v-7.748a.212.212,0,0,1,.1-.177l6.731-3.884a.2.2,0,0,1,.2,0,.2.2,0,0,1,.1.176v7.747a.2.2,0,0,1-.1.177l-6.729,3.885a.181.181,0,0,1-.1.028" fill="#fff" opacity="0.4" style="isolation: isolate"></path></g><g><path d="M154.024,320.633v21.325c0,2.214,4.956,4.009,11.068,4.009V320.633Z" fill="#0072c6"></path><path d="M164.941,345.966h.152c6.113,0,11.068-1.794,11.068-4.008V320.633h-11.22Z" fill="#0072c6"></path><path d="M164.941,345.966h.152c6.113,0,11.068-1.794,11.068-4.008V320.633h-11.22Z" fill="#fff" opacity="0.15" style="isolation: isolate"></path><path d="M176.161,320.633c0,2.214-4.956,4.008-11.068,4.008s-11.068-1.795-11.068-4.008,4.956-4.008,11.068-4.008,11.068,1.795,11.068,4.008" fill="#fff"></path><path d="M173.9,320.4c0,1.462-3.942,2.645-8.805,2.645s-8.806-1.183-8.806-2.645,3.943-2.645,8.806-2.645,8.805,1.184,8.805,2.645" fill="#7fba00"></path><path d="M172.053,322.018c1.153-.447,1.845-1.007,1.845-1.615,0-1.462-3.942-2.646-8.806-2.646s-8.805,1.184-8.805,2.646c0,.608.693,1.168,1.845,1.615a24.074,24.074,0,0,1,13.92,0" fill="#b8d432"></path><path d="M161.577,335.435a1.818,1.818,0,0,1-.721,1.54,3.233,3.233,0,0,1-1.992.546,3.789,3.789,0,0,1-1.808-.39v-1.559a2.789,2.789,0,0,0,1.846.712,1.256,1.256,0,0,0,.753-.195.61.61,0,0,0,.266-.517.723.723,0,0,0-.256-.55,4.7,4.7,0,0,0-1.04-.6,2.292,2.292,0,0,1-1.6-2.046,1.847,1.847,0,0,1,.7-1.508,2.842,2.842,0,0,1,1.851-.567,4.624,4.624,0,0,1,1.7.268v1.456a2.763,2.763,0,0,0-1.607-.487,1.19,1.19,0,0,0-.716.192.606.606,0,0,0-.263.514.734.734,0,0,0,.212.543,3.428,3.428,0,0,0,.869.524,4.307,4.307,0,0,1,1.4.94A1.751,1.751,0,0,1,161.577,335.435Z" fill="#fff"></path><path d="M169.093,333.857a3.985,3.985,0,0,1-.56,2.138,2.99,2.99,0,0,1-1.578,1.271l2.026,1.876h-2.046l-1.447-1.622a3.392,3.392,0,0,1-1.678-.492,3.083,3.083,0,0,1-1.154-1.254,3.849,3.849,0,0,1-.407-1.776,4.15,4.15,0,0,1,.441-1.936,3.131,3.131,0,0,1,1.24-1.308,3.622,3.622,0,0,1,1.832-.458,3.37,3.37,0,0,1,1.727.443A3.024,3.024,0,0,1,168.671,332,3.987,3.987,0,0,1,169.093,333.857Zm-1.656.088a2.733,2.733,0,0,0-.463-1.678,1.5,1.5,0,0,0-1.267-.617,1.59,1.59,0,0,0-1.31.618,3.006,3.006,0,0,0-.01,3.28,1.55,1.55,0,0,0,1.281.611,1.571,1.571,0,0,0,1.291-.592A2.51,2.51,0,0,0,167.437,333.945Z" fill="#fff"></path><polygon fill="#fff" points="174.407 337.398 170.247 337.398 170.247 330.414 171.821 330.414 171.821 336.122 174.407 336.122 174.407 337.398"></polygon></g></g><rect fill="#f0f" height="78.867" opacity="0" width="62.47" x="121.418" y="304.675"></rect></g><g><g><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(479.773 431.273)">Virtual Network</text><g><path d="M540.275,404.95a1.081,1.081,0,0,0,0-1.422l-1.9-1.9-8.532-8.295a.909.909,0,0,0-1.343,0h0a.939.939,0,0,0,0,1.422l8.927,8.769a1,1,0,0,1,0,1.422l-9.085,9.085a1,1,0,0,0,0,1.422h0a.978.978,0,0,0,1.343,0l8.453-8.374.079-.079Z" fill="#3999c6"></path><path d="M501.25,404.95a1.081,1.081,0,0,1,0-1.422l1.9-1.9,8.532-8.295a.909.909,0,0,1,1.343,0h0a.939.939,0,0,1,0,1.422l-8.769,8.769a1,1,0,0,0,0,1.422l8.927,9.085a1,1,0,0,1,0,1.422h0a.978.978,0,0,1-1.343,0l-8.611-8.295-.079-.079Z" fill="#3999c6"></path><path d="M515.391,404.239a2.629,2.629,0,0,1-2.607,2.607,2.891,2.891,0,0,1-2.765-2.607,2.667,2.667,0,0,1,2.765-2.607A2.578,2.578,0,0,1,515.391,404.239Z" fill="#7fba00"></path><path d="M523.37,404.239a2.629,2.629,0,0,1-2.607,2.607A2.891,2.891,0,0,1,518,404.239a2.773,2.773,0,0,1,2.765-2.607A2.629,2.629,0,0,1,523.37,404.239Z" fill="#7fba00"></path><circle cx="528.821" cy="404.239" fill="#7fba00" r="2.607"></circle></g></g><rect fill="#f0f" height="41.257" opacity="0" width="86.986" x="477.145" y="392.041"></rect></g><g><g><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(632.737 363.429)">SQL Server<tspan x="2.49" y="14.4">2016 VM*</tspan></text><g><path d="M662.171,334.029H651.744c1.253,4.424-.43,5.058-7.8,5.058V341.4h25.073v-2.316c-7.373,0-8.1-.632-6.842-5.058" fill="#7a7a7a"></path><path d="M673.333,306.009H639.387a2.169,2.169,0,0,0-2.084,2.183v23.673a2.157,2.157,0,0,0,2.084,2.165h33.947a2.37,2.37,0,0,0,2.317-2.165V308.193a2.378,2.378,0,0,0-2.317-2.183" fill="#a0a1a2"></path><path d="M673.357,306.012l-.024,0H639.386a2.168,2.168,0,0,0-2.084,2.183v23.672a2.157,2.157,0,0,0,2.084,2.166h.808Z" fill="#fff" opacity="0.2" style="isolation: isolate"></path><polygon fill="#59b4d9" points="672.657 308.96 672.657 331.08 640.209 331.08 640.209 308.96 672.657 308.96"></polygon><polygon fill="#59b4d9" points="640.209 331.08 640.254 331.08 640.254 308.961 669.919 308.917 669.921 308.917 640.209 308.961 640.209 331.08"></polygon><rect fill="#a0a1a2" height="2.317" width="25.073" x="643.94" y="339.086"></rect><path d="M656.873,307.616a.544.544,0,1,1-.545-.545.545.545,0,0,1,.545.545" fill="#b8d432"></path><path d="M656.895,319.35a.213.213,0,0,1-.1-.029l-6.752-3.9a.208.208,0,0,1-.1-.177.2.2,0,0,1,.1-.176l6.712-3.872a.205.205,0,0,1,.2,0l6.754,3.9a.205.205,0,0,1,0,.353L657,319.32a.207.207,0,0,1-.1.029" fill="#fff"></path><path d="M655.925,328.823a.193.193,0,0,1-.1-.028l-6.732-3.885a.2.2,0,0,1-.1-.177v-7.8a.207.207,0,0,1,.31-.177l6.731,3.884a.214.214,0,0,1,.1.179v7.8a.208.208,0,0,1-.1.177.215.215,0,0,1-.1.028" fill="#fff" opacity="0.7" style="isolation: isolate"></path><path d="M657.83,328.823a.22.22,0,0,1-.106-.028.208.208,0,0,1-.1-.177V320.87a.212.212,0,0,1,.1-.177l6.731-3.884a.2.2,0,0,1,.2,0,.2.2,0,0,1,.1.176v7.747a.2.2,0,0,1-.1.177l-6.729,3.885a.181.181,0,0,1-.1.028" fill="#fff" opacity="0.4" style="isolation: isolate"></path></g><g><path d="M661.968,320.854v21.325c0,2.214,4.956,4.009,11.068,4.009V320.854Z" fill="#0072c6"></path><path d="M672.885,346.187h.152c6.113,0,11.068-1.794,11.068-4.008V320.854h-11.22Z" fill="#0072c6"></path><path d="M672.885,346.187h.152c6.113,0,11.068-1.794,11.068-4.008V320.854h-11.22Z" fill="#fff" opacity="0.15" style="isolation: isolate"></path><path d="M684.1,320.854c0,2.214-4.956,4.008-11.068,4.008s-11.068-1.795-11.068-4.008,4.956-4.008,11.068-4.008,11.068,1.795,11.068,4.008" fill="#fff"></path><path d="M681.842,320.623c0,1.462-3.942,2.645-8.805,2.645s-8.806-1.183-8.806-2.645,3.943-2.645,8.806-2.645,8.805,1.184,8.805,2.645" fill="#7fba00"></path><path d="M680,322.24c1.153-.447,1.845-1.007,1.845-1.615,0-1.462-3.942-2.646-8.806-2.646s-8.805,1.184-8.805,2.646c0,.608.693,1.168,1.845,1.615a24.074,24.074,0,0,1,13.92,0" fill="#b8d432"></path><path d="M669.521,335.656a1.818,1.818,0,0,1-.721,1.54,3.233,3.233,0,0,1-1.992.546,3.789,3.789,0,0,1-1.808-.39v-1.559a2.789,2.789,0,0,0,1.846.712,1.256,1.256,0,0,0,.753-.195.61.61,0,0,0,.266-.517.723.723,0,0,0-.256-.55,4.7,4.7,0,0,0-1.04-.6,2.292,2.292,0,0,1-1.6-2.046,1.847,1.847,0,0,1,.7-1.508,2.842,2.842,0,0,1,1.851-.567,4.624,4.624,0,0,1,1.7.268v1.456a2.763,2.763,0,0,0-1.607-.487,1.19,1.19,0,0,0-.716.192.606.606,0,0,0-.263.514.734.734,0,0,0,.212.543,3.428,3.428,0,0,0,.869.524,4.307,4.307,0,0,1,1.4.94A1.751,1.751,0,0,1,669.521,335.656Z" fill="#fff"></path><path d="M677.037,334.078a3.985,3.985,0,0,1-.56,2.138,2.99,2.99,0,0,1-1.578,1.271l2.026,1.876h-2.046l-1.447-1.622a3.392,3.392,0,0,1-1.678-.492A3.083,3.083,0,0,1,670.6,336a3.849,3.849,0,0,1-.407-1.776,4.15,4.15,0,0,1,.441-1.936,3.131,3.131,0,0,1,1.24-1.308,3.622,3.622,0,0,1,1.832-.458,3.37,3.37,0,0,1,1.727.443,3.024,3.024,0,0,1,1.183,1.261A3.987,3.987,0,0,1,677.037,334.078Zm-1.656.088a2.733,2.733,0,0,0-.463-1.678,1.5,1.5,0,0,0-1.267-.617,1.59,1.59,0,0,0-1.31.618,3.006,3.006,0,0,0-.01,3.28,1.55,1.55,0,0,0,1.281.611,1.571,1.571,0,0,0,1.291-.592A2.51,2.51,0,0,0,675.381,334.166Z" fill="#fff"></path><polygon fill="#fff" points="682.351 337.62 678.191 337.62 678.191 330.635 679.764 330.635 679.764 336.344 682.351 336.344 682.351 337.62"></polygon></g></g><rect fill="#f0f" height="77.382" opacity="0" width="61.615" x="630.122" y="304.675"></rect></g><g><g><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(641.063 215.415)">IIS VM*</text><g><path d="M667.931,190.7H655.816c1.456,5.139-.5,5.876-9.066,5.876v2.691h29.13v-2.691c-8.566,0-9.407-.734-7.949-5.876" fill="#7a7a7a"></path><path d="M680.9,158.143H641.46a2.52,2.52,0,0,0-2.421,2.537v27.5a2.506,2.506,0,0,0,2.421,2.515H680.9a2.753,2.753,0,0,0,2.692-2.515v-27.5a2.763,2.763,0,0,0-2.692-2.537" fill="#a0a1a2"></path><path d="M680.926,158.146l-.028,0h-39.44a2.519,2.519,0,0,0-2.421,2.537v27.5a2.506,2.506,0,0,0,2.421,2.516h.938Z" fill="#fff" opacity="0.2" style="isolation: isolate"></path><polygon fill="#59b4d9" points="680.113 161.572 680.113 187.27 642.415 187.27 642.415 161.572 680.113 161.572"></polygon><polygon fill="#59b4d9" points="642.415 187.27 642.467 187.27 642.467 161.573 676.932 161.521 676.934 161.521 642.415 161.573 642.415 187.27"></polygon><rect fill="#a0a1a2" height="2.692" width="29.13" x="646.75" y="196.571"></rect><path d="M661.776,160.01a.632.632,0,1,1-.633-.633.633.633,0,0,1,.633.633" fill="#b8d432"></path><path d="M661.8,173.641a.248.248,0,0,1-.119-.034l-7.845-4.528a.241.241,0,0,1-.118-.206.238.238,0,0,1,.118-.2l7.8-4.5a.239.239,0,0,1,.234,0l7.847,4.53a.238.238,0,0,1,0,.41l-7.795,4.5a.24.24,0,0,1-.12.034" fill="#fff"></path><path d="M660.673,184.647a.224.224,0,0,1-.119-.032l-7.821-4.514a.232.232,0,0,1-.121-.206v-9.058a.241.241,0,0,1,.36-.206l7.821,4.512a.249.249,0,0,1,.116.208v9.058a.242.242,0,0,1-.116.206.25.25,0,0,1-.119.032" fill="#fff" opacity="0.7" style="isolation: isolate"></path><path d="M662.888,184.647a.256.256,0,0,1-.123-.032.241.241,0,0,1-.115-.206v-9a.246.246,0,0,1,.115-.206l7.821-4.512a.232.232,0,0,1,.235,0,.235.235,0,0,1,.12.2v9a.233.233,0,0,1-.12.206L663,184.615a.211.211,0,0,1-.115.032" fill="#fff" opacity="0.4" style="isolation: isolate"></path></g></g><rect fill="#f0f" height="64.505" opacity="0" width="48.117" x="636.988" y="155.288"></rect></g><g><g><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(495.037 277.969)">Double-<tspan letter-spacing="-0.112em" x="43.271" y="0">T</tspan><tspan x="48.211" y="0">ake</tspan><tspan x="14.725" y="14.4">DR VM</tspan></text><g><path d="M534.667,252.774H522.552c1.456,5.139-.5,5.876-9.066,5.876v2.691h29.13v-2.691c-8.566,0-9.407-.734-7.949-5.876" fill="#7a7a7a"></path><path d="M547.635,220.221H508.2a2.52,2.52,0,0,0-2.421,2.537v27.5a2.506,2.506,0,0,0,2.421,2.515h39.439a2.753,2.753,0,0,0,2.692-2.515v-27.5a2.763,2.763,0,0,0-2.692-2.537" fill="#a0a1a2"></path><path d="M547.662,220.224l-.028,0H508.2a2.519,2.519,0,0,0-2.421,2.537v27.5a2.506,2.506,0,0,0,2.421,2.516h.938Z" fill="#fff" opacity="0.2" style="isolation: isolate"></path><polygon fill="#59b4d9" points="546.849 223.65 546.849 249.348 509.151 249.348 509.151 223.65 546.849 223.65"></polygon><polygon fill="#59b4d9" points="509.151 249.348 509.203 249.348 509.203 223.651 543.668 223.599 543.67 223.599 509.151 223.651 509.151 249.348"></polygon><rect fill="#a0a1a2" height="2.692" width="29.13" x="513.486" y="258.65"></rect><path d="M528.511,222.088a.632.632,0,1,1-.633-.633.633.633,0,0,1,.633.633" fill="#b8d432"></path><path d="M528.536,235.72a.248.248,0,0,1-.119-.034l-7.845-4.528a.241.241,0,0,1-.118-.206.238.238,0,0,1,.118-.2l7.8-4.5a.239.239,0,0,1,.234,0l7.847,4.53a.238.238,0,0,1,0,.41l-7.795,4.5a.24.24,0,0,1-.12.034" fill="#fff"></path><path d="M527.409,246.726a.224.224,0,0,1-.119-.032l-7.821-4.514a.232.232,0,0,1-.121-.206v-9.058a.241.241,0,0,1,.36-.206l7.821,4.512a.249.249,0,0,1,.116.208v9.058a.242.242,0,0,1-.116.206.25.25,0,0,1-.119.032" fill="#fff" opacity="0.7" style="isolation: isolate"></path><path d="M529.623,246.726a.256.256,0,0,1-.123-.032.241.241,0,0,1-.115-.206v-9a.246.246,0,0,1,.115-.206l7.821-4.512a.232.232,0,0,1,.235,0,.235.235,0,0,1,.12.2v9a.233.233,0,0,1-.12.206l-7.818,4.514a.211.211,0,0,1-.115.032" fill="#fff" opacity="0.4" style="isolation: isolate"></path></g></g><rect fill="#f0f" height="61.615" opacity="0" width="70.569" x="493.562" y="218.38"></rect></g><g><g><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(120.121 77.733)">Customers</text><g><path d="M164.228,30.007a8.158,8.158,0,1,1-8.159-8.158,8.158,8.158,0,0,1,8.159,8.158" fill="#59b4d9"></path><polygon fill="#59b4d9" points="162.034 40.961 156.069 49.319 150.104 40.961 143.897 40.961 143.897 61.57 168.241 61.57 168.241 40.961 162.034 40.961"></polygon><path d="M139.709,43.7a4.584,4.584,0,1,1-4.584-4.583,4.582,4.582,0,0,1,4.584,4.583" fill="#59b4d9"></path><polygon fill="#59b4d9" points="138.476 49.993 135.126 54.689 131.775 49.993 128.287 49.993 128.287 61.57 141.964 61.57 141.964 49.993 138.476 49.993"></polygon><path d="M147.911,30.007a8.153,8.153,0,0,0,7.958,8.148l2.049-16.087a8.132,8.132,0,0,0-10.007,7.939" fill="#fff" opacity="0.2" style="isolation: isolate"></path><polygon fill="#fff" opacity="0.2" points="150.105 40.961 143.896 40.961 143.896 61.57 152.925 61.57 154.726 47.438 150.105 40.961" style="isolation: isolate"></polygon><path d="M130.543,43.7a4.582,4.582,0,0,0,4.583,4.582c.16,0,.309-.03.465-.046l1.124-8.82a4.55,4.55,0,0,0-6.172,4.284" fill="#fff" opacity="0.2" style="isolation: isolate"></path><polygon fill="#fff" opacity="0.2" points="131.775 49.993 128.288 49.993 128.288 61.57 133.931 61.57 134.857 54.311 131.775 49.993" style="isolation: isolate"></polygon></g></g><rect fill="#f0f" height="63.725" opacity="0" width="59.384" x="118.422" y="17.854"></rect></g><g><g><text fill="#5d5d5d" font-family="SegoeUI, Segoe UI" font-size="12" transform="translate(331.042 77.733)"><tspan letter-spacing="-0.087em">T</tspan><tspan x="5.244" y="0">raffic Manager</tspan><tspan x="3.144" y="14.4">(DNS </tspan><tspan letter-spacing="-0.029em" x="33.817" y="14.4">R</tspan><tspan x="40.644" y="14.4">outing)</tspan></text><g><polygon fill="#804998" points="399.05 44.628 399.05 22.061 383.261 6.319 360.916 6.319 345.094 22.537 345.094 44.548 360.884 60.275 383.261 60.275 399.05 44.628"></polygon><path d="M382.365,8.477H361.808L347.252,23.4v20.25L361.78,58.117h20.586l14.526-14.4V22.96ZM381.14,55.138h-.164L368.8,42.787l2.57-2.873H362.55v9.045l2.889-3.11,9.57,9.289h-12L350.231,42.411V24.61l3.585-3.676,9.528,8.584-5.427,5.634h17.33V17.936l-5.665,5.649L359.993,14.6l3.071-3.148h18.07L393.914,24.2V40.108l-6.067-5.717,4.444-4H380.007v11.6l4.014-3.983,6.872,7.462Z" fill="#fff" opacity="0.8" style="isolation: isolate"></path><polygon fill="#fff" opacity="0.2" points="391.384 14.419 383.261 6.319 360.916 6.319 345.094 22.537 345.094 44.549 353.191 52.612 391.384 14.419" style="isolation: isolate"></polygon></g></g><rect fill="#f0f" height="96.563" opacity="0" width="83.417" x="330.363"></rect></g><g><g><path d="M327.559,211.18h4.768c2.864,0,5.016,1.8,5.016,5.465,0,3.2-1.641,5.589-5.016,5.589h-4.768Zm2.431,9.01h2.167c1.409,0,2.756-.867,2.756-3.313,0-2.23-.774-3.654-3.189-3.654H329.99Z"></path><path d="M342.251,214.013a4.22,4.22,0,1,1-4.133,4.226A3.93,3.93,0,0,1,342.251,214.013Zm0,6.781c1.5,0,1.951-1.284,1.951-2.554s-.449-2.569-1.951-2.569c-1.486,0-1.935,1.285-1.935,2.569S340.765,220.793,342.251,220.793Z"></path><path d="M354.9,222.233h-2.09v-1.114h-.047a2.854,2.854,0,0,1-2.446,1.331c-2.338,0-2.926-1.316-2.926-3.3v-4.923h2.2v4.52c0,1.316.387,1.966,1.409,1.966,1.192,0,1.7-.665,1.7-2.291v-4.2h2.2Z"></path><path d="M356.141,211.18h2.2V215.2h.031a2.955,2.955,0,0,1,2.523-1.192c1.594,0,3.313,1.285,3.313,4.211s-1.719,4.226-3.313,4.226a2.771,2.771,0,0,1-2.632-1.239h-.031v1.022h-2.09Zm3.994,4.49c-1.3,0-1.874,1.222-1.874,2.569s.573,2.554,1.874,2.554,1.873-1.222,1.873-2.554S361.435,215.669,360.136,215.669Z"></path><path d="M365.229,211.18h2.2v11.054h-2.2Z"></path><path d="M370.541,218.765c.062,1.393.743,2.028,1.966,2.028a1.809,1.809,0,0,0,1.733-1.037h1.935a3.6,3.6,0,0,1-3.746,2.694,3.909,3.909,0,0,1-4.087-4.211,4.013,4.013,0,0,1,4.087-4.226c2.724,0,4.041,2.291,3.886,4.753Zm3.576-1.393c-.2-1.115-.681-1.7-1.749-1.7a1.731,1.731,0,0,0-1.827,1.7Z"></path><path d="M377.167,217.062h4.66v1.888h-4.66Z"></path><path d="M384.2,213.223h-3.313V211.18h9.056v2.043h-3.313v9.01H384.2Z" fill="#ed2024"></path><path d="M388.742,216.691c.124-2.059,1.966-2.678,3.761-2.678,1.595,0,3.515.356,3.515,2.276v4.164a4.1,4.1,0,0,0,.279,1.78h-2.23a3.28,3.28,0,0,1-.155-.774,3.669,3.669,0,0,1-2.694.991c-1.517,0-2.724-.758-2.724-2.4,0-1.812,1.363-2.245,2.724-2.431s2.6-.155,2.6-1.053c0-.945-.65-1.084-1.424-1.084-.836,0-1.378.341-1.456,1.208Zm5.078,1.625a4.364,4.364,0,0,1-1.827.465c-.682.139-1.3.372-1.3,1.176,0,.821.635,1.022,1.347,1.022a1.634,1.634,0,0,0,1.78-1.842Z" fill="#ed2024"></path><path d="M397.489,211.18h2.2v5.929l2.771-2.879h2.6l-3.019,2.942,3.36,5.062h-2.663l-2.2-3.576-.851.82v2.756h-2.2Z" fill="#ed2024"></path><path d="M407.017,218.765c.062,1.393.743,2.028,1.966,2.028a1.809,1.809,0,0,0,1.733-1.037h1.935a3.6,3.6,0,0,1-3.746,2.694,3.909,3.909,0,0,1-4.087-4.211,4.013,4.013,0,0,1,4.087-4.226c2.724,0,4.041,2.291,3.886,4.753Zm3.576-1.393c-.2-1.115-.681-1.7-1.749-1.7a1.731,1.731,0,0,0-1.827,1.7Z" fill="#ed2024"></path><g><path d="M354.869,227.425h6.345c5.7,0,8.884,2.849,8.884,8.806,0,6.19-2.719,9.686-8.884,9.686h-6.345Zm2.46,16.42h4.092c1.684,0,6.216-.466,6.216-7.277,0-4.4-1.631-7.07-6.164-7.07h-4.144Z"></path><path d="M372.374,227.425h8.7c3.471,0,5.62,1.891,5.62,4.844,0,2.227-.984,4.066-3.211,4.687v.052c2.15.414,2.59,1.994,2.771,3.807.156,1.813.052,3.833,1.088,5.1H384.6c-.7-.751-.311-2.745-.673-4.558-.258-1.812-.7-3.341-3.082-3.341h-6.009v7.9h-2.46Zm7.588,8.521c2.3,0,4.273-.6,4.273-3.289,0-1.813-.984-3.159-3.289-3.159h-6.112v6.448Z"></path></g><g><path d="M388.658,226.993h-.7v-.234h1.668v.234h-.7v1.852h-.278Z"></path><path d="M389.785,226.759h.38l.657,1.753.66-1.753h.38v2.086H391.6v-1.736h-.006l-.651,1.736H390.7l-.651-1.736h-.006v1.736h-.263Z"></path></g><path d="M414.183,211.211a2.281,2.281,0,1,1-2.3,2.269A2.268,2.268,0,0,1,414.183,211.211Zm0,4.227a1.947,1.947,0,1,0-1.885-1.958A1.882,1.882,0,0,0,414.183,215.438Zm-.89-3.282h1.03c.635,0,.933.25.933.762a.686.686,0,0,1-.7.726l.762,1.177h-.445l-.726-1.146h-.439v1.146h-.415Zm.415,1.183h.433c.366,0,.7-.018.7-.439,0-.354-.3-.409-.586-.409h-.548Z"></path></g><rect fill="#f0f" height="41.317" opacity="0" width="89.252" x="327.218" y="206.857"></rect></g></svg>

## Components
* DNS traffic is routed via [Traffic Manager](https://azure.microsoft.com/services/traffic-manager/) which can easily move traffic from one site to another based on policies defined by your organization.
* [VPN Gateway](https://azure.microsoft.com/services/vpn-gateway/): The VPN gateway maintains the communication between the on-premises network and the cloud network securely and privately.
* [Virtual Network](https://azure.microsoft.com/services/virtual-network/): The virtual network is where the failover site will be created when a disaster occurs.

## Next Steps
* [Configure Failover routing method](https://docs.microsoft.com/api/Redirect/documentation/articles/traffic-manager-configure-failover-routing-method/)
* [Create a VNet with a Site-to-Site connection using the Azure portal](https://docs.microsoft.com/api/Redirect/documentation/articles/vpn-gateway-howto-site-to-site-resource-manager-portal/)
* [Designing your network infrastructure for disaster recovery](https://docs.microsoft.com/api/Redirect/documentation/articles/site-recovery-network-design/)

[!INCLUDE [js_include_file](../../_js/index.md)]
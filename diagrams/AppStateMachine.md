# State Machine for the lume App

![](http://www.plantuml.com/plantuml/png/ZLJ1RjGm4BtxA-QC576FsbLXeU84QYbSgXu6PxAnSEp87dUfLlrtd5YEHYHIoQ6gP-OzlpUpdfl863YDLereN1zm98WZs3GIu3GfzVZk2Ph7oURiKtE0tWJwQUYiL0OohUTBFVlm-zQ4o1-cwUfA3zveEXmsBA9AoGCqmPm6pYN6SV3VTI1oq49lIlv79BY-1Ww9bCH9SlP13z_wVeFgqKPI0B2gXbm-uhJysuB3PtD2BYN5JkMwBB75HHKODRg7EVtrzYWGCZoZoYUZqC94mVZEQBJsPSdD7O6SQnxm57THJPhafNVtCqsW6E7kllcOcBtRnrMznOfhGNl7g1bYqZhZ-sGNuAim8QwH7jRWcnRWR7W07WWqZXHmZqJEJ2gklexMHu9gROl_RsV5NVcxcQrRHrlvue21zYOhudAqCjp2_5lxuYCtHmnTytbC5jbu1-nB9M2vU1ylUb8I-tEkXgGoCQeQQE6JYPdlPSPgtz4RAlwPYHG6UrFPTFUrR87wfXP1zG1YUyZ79ajMmH5ueBA5SgxoogLmAJkbl0fhka8aUZB7e2YGNuatdJ-xYfpLq1-6Nukfzzddi_4f5iFKxLF8JWbR5YDBjWt9tAIwLJB7OBgEnDfogfB9f32-Nr0xg6x8TMcqVm40)

<!--
@startuml
mainframe sm lume app

[*] -[plain]-> fireView

state fireView{
state forkFirstApp<<choice>>
[*] -[plain]-> forkFirstApp
forkFirstApp -right-> introScreen : firstAppUse == true
forkFirstApp -[plain]-> torchOff: firstAppUse == false
    fireView -> mapView : navigate
    state torchOff{
    [*] -right-> scanTorchNFC
    state scanTorchNFC{
        scanTorchNFC : periodically scan for NFC-Tags
        scanTorchNFC-up-> scanTorchQR : press QR-Button
        scanTorchNFC-right-> torchOn: contact successful
    }
    state scanTorchQR{
        scanTorchQR : periodically scan for NFC-Tags with the camera
        scanTorchQR -[plain]-> scanTorchNFC: press Close Button
        scanTorchQR-right-> torchOn: contact successful
        }
    }

    state torchOn{
    [*]-right->shareTorchNFC
    state shareTorchNFC{
        shareTorchNFC: Use Host-Card-Emulation to share a torch
        shareTorchNFC -[plain]-> shareQR : press QR-Button
    }
    state shareQR{
        shareQR: Display QR-code to share a torch
        shareQR -[plain]-> shareTorchNFC : press Close Button
        }
    }
}
state mapView{
    mapView -> fireView : navigate
    mapView : Displays the lume map
}
state introScreen{
[*] -up-> slide
        state slide {
                slide -down-> slide : next button/previous pressed
                slide -[plain]-> fireView : last next button pressed
        }
}
torchOff -[hidden]-> torchOn
fireView -[hidden]-> introScreen
fireView -[hidden]-> mapView

@enduml
-->

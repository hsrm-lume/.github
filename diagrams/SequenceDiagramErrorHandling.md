# Sequence Diagram for ErrorHandling

Sequence Diagram for ErrorHandling in the App:

![](http://www.plantuml.com/plantuml/png/hLHDJy904BttLuoSoW4JhqG8CM9Cr1FUaCFQ7UZ6xRRPsOhyUzjfSDDbKI4quICxxxtPDw-P6JbXNLtef13AhAqe44Z2tDhIGYwCrCfi4bsM5MIw90HHLGaqpoApY8PWD8K5sa-L8S4OiXop3y2MJGmJse71RNUKGFTuHiFcLezj9xGmxdeY7wPCUjrLEDmp--YGtUiF-AN8xObyaUxSb0wK0UshSUa1mvyRsFW5YSG6dt2tN0sQDbLDUUnsQ2J_Hqq8kY7vKVnft68HTttQrNugC86rqWvjUXKeef6z26z7erw6jRLeN9ZYkjQQc166wTy4ZvapkNMbIo5JRoM4H2QnGVSGeD9pPh7thwYLMtYvk1ZFuHUryERBrL5JB1MuEeKU6MMZG7cvJGzaRbP3_yv9HOKY4kyQZwV4XJjXuJ0UNul6Sk_bBv9Bg7TUCDuq-j66Vi94_ilpyufItinr8QgK8J2PTXaXUnb6Tez4ZGubLy9Mfws4owy5lngwt_OpQxxgGdy3)

<!--
@startuml
mainframe sd Error handling
loop close app
    Screens -> Services : check errors
    alt new error
        Services -> ErrorHandler : handleError(errorType)
        ErrorHandler -> ErrorHandler : check error exist
        alt error not in list
            ErrorHandler -> "errorList:MessageKey[]" : push(errorType)
        end
    else less errors
        Services -> ErrorHandler : remError(errorType)
        ErrorHandler -> "errorList:MessageKey[]" : errorList = filter(!errorType)
    end
    Screens <-- Services : current errors
    alt fullscreen error
        Screens -> fullscreenErrors: reload()
        fullscreenErrors -> ErrorHandler : getFullscreenErrors()
        ErrorHandler -> "errorList:MessageKey[]" : filter(isFullScreenError)
        ErrorHandler <-- "errorList:MessageKey[]" : fullscreenErrors[]
        fullscreenErrors <-- ErrorHandler : fullscreenErrors[]
        fullscreenErrors -> fullscreenErrors : show(fullscreenErrors[1])
    else dismissable error
        Screens -> errorBar : reload()
        errorBar -> ErrorHandler : getDismissableErrors()
        ErrorHandler -> "errorList:MessageKey[]" : filter(isDismissableError)
        ErrorHandler <-- "errorList:MessageKey[]" : dismissableErrors[]
        errorBar <-- ErrorHandler : dismissableErrors[]
        errorBar -> errorBar : dismissableErrors\n.map(error => show(error))
        alt error deleted
            errorBar-> ErrorHandler : remError(errorType)
            ErrorHandler -> "errorList:MessageKey[]" : errorList = filter(!errorType)
        end
    end
end
@enduml
-->

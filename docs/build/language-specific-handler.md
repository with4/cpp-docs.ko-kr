---
title: 언어별 처리기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6503e0cd-2d3a-4330-a925-8bed8c27c2be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6cbfbe6a9b98828a63fb4a092717bfab583e9a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368800"
---
# <a name="language-specific-handler"></a>언어별 처리기
언어별 처리기의 상대 주소에에서 있으면는 UNWIND_INFO 때마다 UNW_FLAG_EHANDLER 또는 UNW_FLAG_UHANDLER 플래그를 설정 합니다. 이전 섹션에서 설명한 언어별 처리기는 예외 처리기에 대 한 검색의 일부로 또는 해제의 일부로 호출 됩니다. 여기에 다음과 같은 프로토타입이 있습니다.  
  
```  
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (  
    IN PEXCEPTION_RECORD ExceptionRecord,  
    IN ULONG64 EstablisherFrame,  
    IN OUT PCONTEXT ContextRecord,  
    IN OUT PDISPATCHER_CONTEXT DispatcherContext  
);  
```  
  
 **ExceptionRecord** 표준 Win64 정의 하는 예외 레코드에 대 한 포인터를 제공 합니다.  
  
 **EstablisherFrame** 이 함수에 대 한 고정된 스택 할당의 기본 주소입니다.  
  
 **ContextRecord** 지점 (예외 처리기의 경우)에 예외가 발생 한 시간 또는 현재 예외 컨텍스트를 "해제" 컨텍스트 (종료 처리기의 경우).  
  
 **DispatcherContext** 이 함수에 대 한 발송자 컨텍스트를 가리킵니다. 여기에 다음 정의가 있습니다.  
  
```  
typedef struct _DISPATCHER_CONTEXT {  
    ULONG64 ControlPc;  
    ULONG64 ImageBase;  
    PRUNTIME_FUNCTION FunctionEntry;  
    ULONG64 EstablisherFrame;  
    ULONG64 TargetIp;  
    PCONTEXT ContextRecord;  
    PEXCEPTION_ROUTINE LanguageHandler;  
    PVOID HandlerData;  
} DISPATCHER_CONTEXT, *PDISPATCHER_CONTEXT;  
```  
  
 **ControlPc** 이 함수 내에서 RIP의 값입니다. 이 예외 주소 또는 주소 컨트롤 설정 함수가 중단 합니다. 이이 함수 내에서 일부 보호 된 생성자 내에서 컨트롤 인지 확인 하는 데 사용 될 RIP (예를 들어 __try 블록에 대 한 \__try /\__except 또는 \__try /\__finally).  
  
 **ImageBase** 기본 (부하 주소)의 이미지 함수 항목에 사용 되는 32 비트 오프셋에 추가 되 고 해제 정보를 상대 주소를 기록 하려면이 함수를 포함 하는 모듈은 합니다.  
  
 **FunctionEntry** 는 RUNTIME_FUNCTION에 대 한 포인터를 제공 함수 진입 함수를 보유 하 고이 함수에 대 한 정보 이미지 기본 상대 주소를 해제 합니다.  
  
 **EstablisherFrame** 이 함수에 대 한 고정된 스택 할당의 기본 주소입니다.  
  
 **TargetIp** 해제의 연속 주소를 지정 하는 선택적 명령 주소를 제공 합니다. 이 주소는 무시 됩니다 **EstablisherFrame** 지정 되지 않았습니다.  
  
 **ContextRecord** 시스템 예외 디스패치/해제 코드에서 사용 하기 위해 예외 컨텍스트를 가리킵니다.  
  
 **LanguageHandler** 호출 되는 언어 관련 언어 처리기 루틴을 가리킵니다.  
  
 **HandlerData** 이 함수에 대 한 언어별 처리기 데이터를 가리킵니다.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리(x64)](../build/exception-handling-x64.md)
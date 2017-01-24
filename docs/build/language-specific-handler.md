---
title: "언어별 처리기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 6503e0cd-2d3a-4330-a925-8bed8c27c2be
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 언어별 처리기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

UNW\_FLAG\_EHANDLER 또는 UNW\_FLAG\_UHANDLER 플래그를 설정할 때마다 언어별 처리기의 상대 주소가 UNWIND\_INFO에 표시됩니다.  이전 단원에서 설명한 것처럼 언어별 처리기는 예외 처리기에 대한 검색 또는 해제의 일부로서 호출됩니다.  사용되는 프로토타입은 다음과 같습니다.  
  
```  
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (  
    IN PEXCEPTION_RECORD ExceptionRecord,  
    IN ULONG64 EstablisherFrame,  
    IN OUT PCONTEXT ContextRecord,  
    IN OUT PDISPATCHER_CONTEXT DispatcherContext  
);  
```  
  
 **ExceptionRecord**는 표준 Win64 정의가 있는 예외 레코드에 대한 포인터를 제공합니다.  
  
 **EstablisherFrame**은 이 함수의 고정된 스택 할당에 대한 기본 주소입니다.  
  
 **ContextRecord**는 예외가 발생한 경우 예외 컨텍스트를 가리키거나\(예외 처리기\) 현재 "해제" 컨텍스트를 가리킵니다\(종료 처리기\).  
  
 **DispatcherContext**는 이 함수의 디스패처 컨텍스트를 가리킵니다.  여기에는 다음과 같은 정의가 있습니다.  
  
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
  
 **ControlPc**는 이 함수 내의 RIP 값입니다.  이는 예외 주소이거나 컨트롤에서 설정 함수가 남겨진 주소입니다.  이 값은 컨트롤이 이 함수 내의 보호되는 구문에 포함되어 있는지 확인하는 데 사용되는 RIP입니다\(예: \_\_try\/\_\_except 또는 \_\_try\/\_\_finally의 \_\_try 블록\).  
  
 **ImageBase**는 이 함수가 포함된 모듈의 이미지 기준\(로드 주소\)입니다. 이 값은 상대 주소를 기록하기 위해 함수 엔트리와 해제 정보에 사용되는 32비트 오프셋에 추가됩니다.  
  
 **FunctionEntry**는 이 함수에 대한 함수 및 해제 정보 이미지 기준 상대 주소가 저장되는 RUNTIME\_FUNCTION 함수 엔트리에 대한 포인터를 제공합니다.  
  
 **EstablisherFrame**은 이 함수의 고정된 스택 할당에 대한 기본 주소입니다.  
  
 **TargetIp**는 해제의 연속 주소를 지정하는 선택적 명령 주소를 제공합니다.  **EstablisherFrame**을 지정하지 않으면 이 주소가 무시됩니다.  
  
 **ContextRecord**는 시스템 예외 디스패치\/해제 코드에 사용하기 위한 예외 컨텍스트를 가리킵니다.  
  
 **LanguageHandler**는 호출하려는 언어별 처리기 루틴을 가리킵니다.  
  
 **HandlerData**는 이 함수에 대한 언어별 처리기 데이터를 가리킵니다.  
  
## 참고 항목  
 [예외 처리\(x64\)](../build/exception-handling-x64.md)
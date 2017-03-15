---
title: "구조체 UNWIND_INFO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f0aee906-a1b9-44cc-a8ad-463637bd5411
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 구조체 UNWIND_INFO
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

해제 데이터 정보 구조체는 함수가 스택 포인터에 미치는 영향과 스택에서 비volatile 레지스터가 저장되는 위치를 기록하는 데 사용됩니다.  
  
|||  
|-|-|  
|UBYTE: 3|버전|  
|UBYTE: 5|Flags|  
|UBYTE|프롤로그 크기|  
|UBYTE|해제 코드 수|  
|UBYTE: 4|프레임 레지스터|  
|UBYTE: 4|프레임 레지스터 오프셋\(배율 조정\)|  
|USHORT \* n|해제 코드 배열|  
|variable|아래의 \(1\) 또는 \(2\) 형식이 될 수 있음|  
  
 \(1\) 예외 처리기  
  
|||  
|-|-|  
|ULONG|예외 처리기의 주소|  
|variable|언어별 처리기 데이터\(선택적\)|  
  
 \(2\) 연결 된 해제 정보  
  
|||  
|-|-|  
|ULONG|함수 시작 주소|  
|ULONG|함수 끝 주소|  
|ULONG|해제 정보 주소|  
  
 UNWIND\_INFO 구조체는 메모리에 DWORD 정렬되어야 합니다.  각 필드의 의미는 다음과 같습니다.  
  
 **버전**  
 해제 데이터의 버전 번호입니다. 현재 1입니다.  
  
 **Flags**  
 현재 세 가지 플래그가 정의되어 있습니다.  
  
 UNW\_FLAG\_EHANDLER 함수 예외를 검사 하는 데 필요한 함수를 찾을 때 호출 해야 하는 예외 처리기를 있습니다.  
  
 예외를 해제 하는 때 호출 해야 하는 종료 처리기를 UNW\_FLAG\_UHANDLER 함수를 있습니다.  
  
 UNW\_FLAG\_CHAININFO이 해제 정보 구조체는 기본 절차에 대 한 아닙니다.  대신, 연결된 해제 정보 엔트리는 이전 RUNTIME\_FUNCTION 엔트리의 콘텐츠입니다.  연결된 해제 정보 구조체에 대한 설명은 다음 텍스트를 참조하십시오.  이 플래그를 설정한 경우에는 UNW\_FLAG\_EHANDLER 및 UNW\_FLAG\_UHANDLER 플래그를 해제해야 합니다.  또한 프레임 레지스터와 고정 스택 할당 필드의 값은 기본 해제 정보의 값과 동일해야 합니다.  
  
 **프롤로그 크기**  
 함수 프롤로그의 바이트 단위 길이입니다.  
  
 **해제 코드 수**  
 해제 코드 배열의 슬롯 수입니다.  UWOP\_SAVE\_NONVOL 같은 일부 해제 코드를 사용하려면 배열에 슬롯이 두 개 이상 있어야 합니다.  
  
 **프레임 레지스터**  
 0이 아닌 경우 함수에서 프레임 포인터를 사용하고 이 필드는 UNWIND\_CODE 노드의 작업 정보 필드에 대해 동일한 인코딩을 사용하여 프레임 포인터로 사용되는 비volatile 레지스터의 번호가 됩니다.  
  
 **프레임 레지스터 오프셋\(배율 조정\)**  
 프레임 레지스터 필드가 0이 아닌 경우 이 필드는 이를 설정할 때 FP 레지스터에 적용되는 RSP에서 배율 조정하여 오프셋됩니다.  실제 FP 레지스터는 \(RSP \+ 16 \* 이 필드의 값\)으로 설정되며 오프셋 범위는 0에서 240까지입니다.  따라서 FP 레지스터가 동적 스택 프레임의 로컬 스택 할당의 중간을 가리키게 되므로 짧은 명령을 통해 코드를 간결하게 만들 수 있습니다. 명령이 길면 부호 있는 8비트 오프셋 형식을 사용할 수 있습니다.  
  
 **해제 코드 배열**  
 비volatile 레지스터와 RSP에 대한 프롤로그의 영향을 설명하는 항목의 배열입니다.  개별 항목의 의미는 UNWIND\_CODE에 대한 설명을 참조하십시오.  맞춤을 위해 이 배열의 엔트리 수는 항상 짝수이며 마지막 엔트리는 사용되지 않을 수 있습니다. 마지막 엔트리를 사용하지 않는 경우 배열은 해제 코드 필드의 수에서 지정한 것보다 하나 더 길어집니다.  
  
 **예외 처리기의 주소**  
 UNW\_FLAG\_CHAININFO 플래그를 해제하고 UNW\_FLAG\_EHANDLER 또는 UNW\_FLAG\_UHANDLER 플래그 중 하나를 설정한 경우 함수의 언어별 예외\/종료 처리기에 대한 이미지를 기준으로 한 포인터입니다.  
  
 **언어별 처리기 데이터**  
 함수의 언어별 예외 처리기 데이터입니다.  이 데이터의 형식은 지정되어 있지 않으며 사용 중인 특정 예외 처리기에 따라 전적으로 결정됩니다.  
  
 **연결된 해제 정보**  
 UNW\_FLAG\_CHAININFO 플래그를 설정한 경우 UNWIND\_INFO 구조체는 세 개의 UWORD로 끝납니다.  이러한 UWORD는 연결된 해제의 함수에 대한 RUNTIME\_FUNCTION 정보를 나타냅니다.  
  
## 참고 항목  
 [예외 처리 및 디버거 지원을 위한 해제 데이터](../build/unwind-data-for-exception-handling-debugger-support.md)
---
title: 구조체 UNWIND_INFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: f0aee906-a1b9-44cc-a8ad-463637bd5411
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1effec5bc753f1b23f8d43a8406c61cb6663fa56
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="struct-unwindinfo"></a>구조체 UNWIND_INFO
해제 데이터 정보 구조체를 사용 하 여 함수에 스택 포인터 및 스택에 비휘발성 레지스터 저장 되는 효과 기록 합니다.  
  
|||  
|-|-|  
|UBYTE: 3|버전|  
|UBYTE: 5|플래그|  
|UBYTE|프롤로그의 크기|  
|UBYTE|해제 코드 수|  
|UBYTE: 4|프레임 레지스터|  
|UBYTE: 4|프레임 배율이 레지스터 오프셋|  
|USHORT * n|해제 코드 배열|  
|변수|폼의 (1) 또는 (2)이 될 수|  
  
 (1) 예외 처리기  
  
|||  
|-|-|  
|ULONG|예외 처리기의 주소|  
|변수|언어별 처리기 데이터 (옵션)|  
  
 (2) 연결 된 해제 정보  
  
|||  
|-|-|  
|ULONG|함수 시작 주소|  
|ULONG|끝 주소 함수|  
|ULONG|정보 주소를 해제 합니다.|  
  
 구조체 UNWIND_INFO DWORD 메모리에 정렬 해야 합니다. 각 필드의 의미는 다음과 같습니다.  
  
 **Version**  
 현재 1 해제 데이터의 버전 번호입니다.  
  
 **플래그**  
 세 가지 플래그 현재 정의 되어 있습니다.  
  
 UNW_FLAG_EHANDLER 함수가 예외를 검사 해야 하는 함수를 찾을 때 호출 해야 하는 예외 처리기를 있습니다.  
  
 UNW_FLAG_UHANDLER 함수에 예외를 해제 하는 때를 호출 해야 하는 종료 처리기입니다.  
  
 UNW_FLAG_CHAININFO이 해제 정보 구조체는 프로시저에 대 한 기본 한 아닙니다. 대신,는 연결 된 해제 정보 항목은 이전 RUNTIME_FUNCTION 항목의 내용입니다. 에 대 한 설명은 다음 텍스트를 참조 하십시오. 연결 된 해제 정보 구조체입니다. 이 플래그가 설정 된 UNW_FLAG_EHANDLER 및 UNW_FLAG_UHANDLER 플래그 해제 해야 합니다. 또한, 프레임 레지스터와 고정 스택 할당 필드 값이 같은 주 에서처럼 해제 정보 있어야 합니다.  
  
 **프롤로그의 크기**  
 함수 프롤로그의 바이트의 길이입니다.  
  
 **해제 코드 수**  
 해제 코드 배열에서 슬롯의 수입니다. 참고 일부 해제 코드 (예를 들어 UWOP_SAVE_NONVOL)는 둘 이상의 슬롯 배열에 필요 합니다.  
  
 **프레임 레지스터**  
 0이 아닌 경우 함수에서 프레임 포인터를 사용 하는 다음 하 고이 필드는 UNWIND_CODE 노드 작업 정보 필드에 대 한 같은 인코딩을 사용 하 여 프레임 포인터로 사용 되는 비휘발성 레지스터 번호입니다.  
  
 **프레임 오프셋 (배율 조정) 등록**  
 프레임 레지스터 필드가 0이 아닌 경우 이것이 설정 될 때 FP 레지스터에 적용 되는 RSP에서 크기 조정 된 오프셋입니다. 실제 FP 레지스터 RSP + 16으로 설정 되어 *이 번호를 240 0에서 오프셋을 사용할 수 있습니다. 이렇게 하면 짧은 명령 (8 비트 부호 있는 오프셋된 형식 자세한 지침 사용할 수 있음)을 통해 향상 된 코드 밀도 허용 하는 동적 스택 프레임에 대 한 로컬 스택 할당의 중간에 FP 레지스터를 가리키고 있습니다.  
  
 **해제 코드 배열**  
 이것이 비휘발성 레지스터 및 rsp 구성에는 프롤로그의 결과 설명 하는 항목의 배열입니다. UNWIND_CODE에 개별 항목의 의미에 대 한 섹션을 참조 합니다. 맞춤을 위해이 배열은 항상 짝수의 수는 항목과 함께 최종 잠재적으로 사용 하지 않는 항목 (있는 경우 배열의 수는 되지 해제 코드 필드의 수에 따라).  
  
 **예외 처리기의 주소**  
 이것이 함수의 언어별 예외/종료 처리기에 대 한 이미지에 상대적인 포인터 (플래그 UNW_FLAG_CHAININFO 만으로도 UNW_FLAG_EHANDLER 또는 UNW_FLAG_UHANDLER 플래그 중 하나가 설정 되어 있으면)입니다.  
  
 **언어별 처리기 데이터**  
 언어별 예외 처리기 데이터는 함수입니다. 이 데이터의 형식은 지정 하지 않으면 이며 완전히 사용 중인 특정 예외 처리기에 의해 결정 됩니다.  
  
 **연결 된 해제 정보**  
 UNW_FLAG_CHAININFO 플래그가 설정 된 경우 UNWIND_INFO 구조 세 UWORDs로 끝납니다.  이러한 UWORDs 연결된 해제의 함수에 대 한 RUNTIME_FUNCTION 정보를 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 지원, 예외 처리를 위한 해제 데이터](../build/unwind-data-for-exception-handling-debugger-support.md)
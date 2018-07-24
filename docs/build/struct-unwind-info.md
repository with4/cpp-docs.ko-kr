---
title: 구조체 UNWIND_INFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f0aee906-a1b9-44cc-a8ad-463637bd5411
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6046dffd74824b05c7b7b10be57bb0b2274ffdc
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207574"
---
# <a name="struct-unwindinfo"></a>구조체 UNWIND_INFO
해제 데이터 정보 구조 함수 스택 포인터 및 비휘발성 레지스터 스택에 저장 되는 위치에 결과 기록 하는 합니다.  
  
|||  
|-|-|  
|UBYTE: 3|버전|  
|UBYTE: 5|플래그|  
|UBYTE|프롤로그의 크기|  
|UBYTE|해제 코드 수|  
|UBYTE: 4|프레임 등록|  
|UBYTE: 4|프레임 등록 오프셋 (확장)|  
|USHORT \* n|해제 코드 배열|  
|변수|폼의 (1) 또는 (2) 아래 중일 수 있습니다|  
  
 (1) 예외 처리기  
  
|||  
|-|-|  
|ULONG|예외 처리기의 주소|  
|변수|언어별 처리기 데이터 (선택 사항)|  
  
 (2) 연결 된 해제 정보  
  
|||  
|-|-|  
|ULONG|함수 시작 주소|  
|ULONG|함수 끝 주소|  
|ULONG|정보 주소를 해제 합니다.|  
  
 UNWIND_INFO 구조 DWORD 메모리에 정렬 해야 합니다. 각 필드의 의미는 다음과 같습니다.  
  
 **Version**  
 현재 1 해제 데이터의 버전 번호입니다.  
  
 **플래그**  
 세 가지 플래그 현재 정의 됩니다.  
  
 UNW_FLAG_EHANDLER 함수는 예외를 검사 해야 하는 함수를 찾을 때 호출 해야 하는 예외 처리기를 있습니다.  
  
 UNW_FLAG_UHANDLER 함수는 예외를 해제 하는 경우를 호출 해야 하는 종료 처리기를 있습니다.  
  
 UNW_FLAG_CHAININFO이 구조가 아닌 기본 프로시저에 대 한 정보를 해제 합니다. 대신 연결 된 해제 정보 항목을 이전 RUNTIME_FUNCTION 항목의 내용입니다. 에 대 한 설명은 다음 텍스트를 보려면 연결 된 해제 정보 구조체입니다. 이 플래그를 설정 하는 경우 다음 UNW_FLAG_EHANDLER 및 UNW_FLAG_UHANDLER 플래그를 지워야 합니다. 또한 프레임 등록 및 고정 스택 할당 필드 해제 정보 주 데이터베이스와 같이 동일한 값을 가져야 합니다.  
  
 **프롤로그의 크기**  
 길이 (바이트)는 함수 프롤로그입니다.  
  
 **해제 코드 수**  
 해제 코드 배열에서 슬롯의 수입니다. 참고 일부 해제 코드 (예를 들어 UWOP_SAVE_NONVOL)는 배열에서 둘 이상의 슬롯이 필요 합니다.  
  
 **프레임 등록**  
 0이 아니면 함수는 프레임에 대 한 포인터를 사용 하는 다음이 고이 필드는 UNWIND_CODE 노드 작업 정보 필드에 대 한 동일한 인코딩을 사용 하 여 프레임 포인터로 사용 비휘발성 레지스터의 수입니다.  
  
 **프레임 오프셋 (확장)를 등록 합니다.**  
 프레임 등록 필드가 0이 아닌 경우 이것이 확장된 RSP 설정 되 면 FP 레지스터에 적용 되는 오프셋입니다. 실제 FP 레지스터 RSP + 16으로 설정 됩니다 \* 이 숫자를 오프셋 0에서 240 허용 합니다. 이렇게 하면 짧은 지침 (자세한 내용은 8 비트 부호 있는 오프셋된 폼을 사용할 수 있음)를 통해 더 나은 코드 밀도 허용 하는 동적 스택 프레임에 대 한 로컬 스택 할당의 중간에 FP 레지스터를 가리키고 있습니다.  
  
 **해제 코드 배열**  
 이것이 비휘발성 레지스터 및 RSP 프롤로그의 결과 설명 하는 항목의 배열입니다. 개별 항목의 의미 UNWIND_CODE에서 섹션을 참조 하십시오. 맞춤을 위해이 배열은 항상 짝수 개의 항목을 잠재적으로 사용 되지 않는 최종 항목을 사용 하 여 (이 경우 배열 수는 해제 코드 필드 수로 표시 된 것 보다 긴 하나).  
  
 **예외 처리기의 주소**  
 이 경우 함수의 언어별 예외/종료 처리기에 대 한 이미지에 상대적인 포인터 (플래그 UNW_FLAG_CHAININFO 맑 설정할지 UNW_FLAG_EHANDLER 또는 UNW_FLAG_UHANDLER 플래그 중 하나).  
  
 **언어별 처리기 데이터**  
 함수의 언어별 예외 처리기 데이터입니다. 이 데이터의 형식은 지정 하지 않으면 이며 사용 중인 특정 예외 처리기에 의해 완전히 결정 됩니다.  
  
 **연결 된 해제 정보**  
 UNW_FLAG_CHAININFO 플래그가 설정 되어 있으면 UNWIND_INFO 구조 세 UWORDs로 끝납니다.  이러한 UWORDs RUNTIME_FUNCTION 정보를 함수에 대 한 연결된 해제를 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 지원, 예외 처리를 위한 해제 데이터](../build/unwind-data-for-exception-handling-debugger-support.md)
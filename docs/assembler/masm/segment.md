---
title: 세그먼트 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- SEGMENT
dev_langs:
- C++
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c55416cc5a757128c9cc97b2f342953911ac2946
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="segment"></a>SEGMENT
호출 프로그램 세그먼트 정의 *이름* 세그먼트 특성이  
  
## <a name="syntax"></a>구문  
  
```  
  
   name SEGMENT [[READONLY]] [[align]] [[combine]] [[use]] [[characteristics]] ALIAS(string) [['class']]  
statements  
name ENDS  
```  
  
#### <a name="parameters"></a>매개 변수  
 *align*  
 범위 시작 주소는 세그먼트를 선택할 수 있는 메모리 주소입니다. 맞춤 유형을 다음 중 하나일 수 있습니다.  
  
|정렬 형식|시작 주소|  
|----------------|----------------------|  
|**BYTE**|다음 사용 가능한 바이트 주소입니다.|  
|**WORD**|다음 사용 가능한 단어 주소 (단어 당 2 바이트)입니다.|  
|**DWORD**|다음 2 배 워드를 사용 가능한 주소 (2 배 워드 당 4 바이트)입니다.|  
|**P A R A**|다음 단락을 사용할 수 있는 주소 (단락 당 16 바이트)입니다.|  
|**PAGE**|다음 사용 가능한 페이지 주소 (페이지당 256 바이트)입니다.|  
|**맞춤**(*n*)|다음 사용 가능한 *n*번째 바이트 주소입니다. 자세한 내용은 설명 섹션을 참조 하십시오.|  
  
 이 매개 변수를 지정 하지 않으면 **P a r a** 기본적으로 사용 됩니다.  
  
 *combine*  
 **PUBLIC**, **STACK**, **COMMON**, **MEMORY**, **AT***address*, **PRIVATE**  
  
 *use*  
 **USE16**, **USE32**, **FLAT**  
  
 `characteristics`  
 **정보**, **읽을**, **쓰기**, **EXECUTE**, **SHARED**, **NOPAGE**, **NOCACHE**, 및 **삭제**  
  
 COFF에 대해서만 지원 됩니다 이러한 및 유사한 이름의 COFF 섹션 특성에 해당 (예를 들어 **SHARED** IMAGE_SCN_MEM_SHARED에 해당). 읽기는 IMAGE_SCN_MEM_READ 플래그를 설정 합니다. 사용 되지 않는 읽기 전용 플래그 IMG_SCN_MEM_WRITE 플래그를 지우려면 섹션을 발생 합니다. 있는 경우 `characteristics` 는 설정의 기본 특성은 사용 되지 않으며 프로그래머가 지정한 플래그만 적용 됩니다.  
  
 `ALIAS(` `string` `)`  
 이 문자열은 내보낸된 COFF 개체의 섹션 이름으로 사용 됩니다.  같은 이름의 외부, 서로 다른 MASM 세그먼트 이름 가진 여러 섹션을 만듭니다.  
  
 지원 되지 않습니다 **/omf**합니다.  
  
 `class`  
 세그먼트 해야 결합 이며 어셈블된 파일의 정렬 방법을 지정 합니다. 일반적인 값은 `'DATA'`, `'CODE'`, `'CONST'` 및 `'STACK'`  
  
## <a name="remarks"></a>설명  
 에 대 한 `ALIGN(n)`, `n` 1에서 8192 개로 2의 배수가 될 수 있습니다; 지원 되지 않습니다 **/omf**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [지시문 참조](../../assembler/masm/directives-reference.md)
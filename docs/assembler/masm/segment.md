---
title: "SEGMENT | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SEGMENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SEGMENT directive"
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# SEGMENT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

호출 프로그램 세그먼트 정의  *이름* 세그먼트 보유  
  
## 구문  
  
```  
  
   name SEGMENT [[READONLY]] [[align]] [[combine]] [[use]] [[characteristics]] ALIAS(string) [['class']]  
statements  
name ENDS  
```  
  
#### 매개 변수  
 *맞춤*  
 해당 범위의 메모리 주소가 세그먼트의 시작 주소를 선택할 수 있습니다.  맞춤 유형을 다음 중 하나가 될 수 있습니다.  
  
|정렬 형식|시작 주소|  
|-----------|-----------|  
|**BYTE**|다음 사용 가능한 바이트 주소입니다.|  
|**WORD**|다음 사용 가능한 word 주소 \(단어 당 2 바이트\)입니다.|  
|**DWORD**|다음 사용 가능한 이중 단어 주소 \(이중 단어 당 4 바이트\)입니다.|  
|**다음 단락**|다음 사용할 수 있는 단락 주소 \(단락 당 16 바이트\)입니다.|  
|**페이지**|다음 페이지를 사용할 수 있는 주소 \(페이지 당 256 바이트\).|  
|**ALIGN**\(*n*\)|다음 사용할 수 있는  *n*번째 바이트 주소입니다.  자세한 내용은 설명 단원을 참조 하십시오.|  
  
 이 매개 변수를 지정 하지 않으면  **PARA** 기본적으로 사용 됩니다.  
  
 *결합*  
 **PUBLIC**, **STACK**, **COMMON**, **MEMORY**, **AT***address*, **PRIVATE**  
  
 *사용*  
 **USE16**, **USE32**, **FLAT**  
  
 `characteristics`  
 **INFO**, **READ**, **WRITE**, **EXECUTE**, **SHARED**, **NOPAGE**, **NOCACHE**, and **DISCARD**  
  
 이 대 한 COFF만 지원 되며 비슷한 이름 COFF 섹션 특성에 해당 \(예를 들어,  **SHARED** IMAGE\_SCN\_MEM\_SHARED에 해당\).  IMAGE\_SCN\_MEM\_READ 플래그를 설정 하는 읽기입니다.  사용 되지 않는 읽기 전용 플래그 섹션 IMG\_SCN\_MEM\_WRITE 플래그를 지우려면 인해 합니다.  있는 경우 `characteristics` , 기본 특성 사용 되지 않고는 프로그래머 지정 플래그가 적용 되지 설정 하는.  
  
 `ALIAS(` `string` `)`  
 이 문자열을 사용 하 여 내보낸 COFF 개체에서 섹션 이름입니다.  같은 외부 이름을 서로 다른 MASM 세그먼트 이름 가진 여러 구역을 만듭니다.  
  
 지원 하지 않습니다 **\/omf**.  
  
 `class`  
 세그먼트 결합 고 어셈블된 파일의 정렬 되어야 방법을 지정 합니다.  Typical values are, `'DATA'`, `'CODE'`, `'CONST'` and`'STACK'`  
  
## 설명  
 For `ALIGN(``n``)`, `n` may be any power of 2 from 1 to 8192; 지원지 않습니다 **\/omf**.  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)
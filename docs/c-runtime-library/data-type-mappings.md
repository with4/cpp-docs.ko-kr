---
title: "데이터 형식 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_TXCHAR"
  - "_TUCHAR"
  - "_TINT"
  - "_TSCHAR"
  - "_TCHAR"
  - "TCHAR::H"
  - "TCHAR"
  - "_T"
  - "_TEXT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_T 형식"
  - "_TCHAR 형식"
  - "_TEXT 형식"
  - "_TINT 형식"
  - "_TSCHAR 형식"
  - "_TUCHAR 형식"
  - "_TXCHAR 형식"
  - "일반 텍스트 데이터 형식"
  - "T 형식"
  - "TCHAR 형식"
  - "TCHAR.H 데이터 형식, 정의된 매핑"
  - "TEXT 형식"
  - "TINT 형식"
  - "TSCHAR 형식"
  - "TUCHAR 형식"
  - "TXCHAR 형식"
ms.assetid: 4e573c05-8800-468b-ae5f-76ff7409835e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 데이터 형식 매핑
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 데이터 형식 매핑은 TCHAR.H에 정의 되어 있으며 상수 `_UNICODE` 또는 `_MBCS`가 프로그램에 정의되어 있는지의 여부에 따라 다릅니다.  
  
 관련 내용은, [Using TCHAR.H Data Types with \_MBCS Code](../text/using-tchar-h-data-types-with-mbcs-code.md)를 참조하십시오.  
  
### 제네릭 텍스트 데이터 형식 매핑  
  
|제네릭 텍스트<br /><br /> 데이터 형식 이름|SBCS \(\_UNICODE,<br /><br /> \_MBCS not<br /><br /> defined\)|\_MBCS<br /><br /> 가 정의됨|\_UNICODE<br /><br /> 가 정의됨|  
|---------------------------|----------------------------------------------------|----------------------|-------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_tfinddata_t`|`_finddata_t`|`_finddata_t`|`_wfinddata_t`|  
|`_tfinddata64_t`|`__finddata64_t`|`__finddata64_t`|`__wfinddata64_t`|  
|`_tfinddatai64_t`|`_finddatai64_t`|`_finddatai64_t`|`_wfinddatai64_t`|  
|`_TINT`|`int`|`int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` 또는 `_TEXT`|적용 안 됨\(전처리기에서 제거\)|적용 안 됨\(전처리기에서 제거\)|`L`\(다음 문자 또는 문자열을 해당 Unicode 로 변환\)|  
  
## 참고 항목  
 [일반 텍스트 매핑](../c-runtime-library/generic-text-mappings.md)   
 [상수 및 전역 변수 매핑](../c-runtime-library/constant-and-global-variable-mappings.md)   
 [루틴 매핑](../c-runtime-library/routine-mappings.md)   
 [샘플 일반 텍스트 프로그램](../c-runtime-library/a-sample-generic-text-program.md)   
 [일반 텍스트 매핑 사용](../c-runtime-library/using-generic-text-mappings.md)
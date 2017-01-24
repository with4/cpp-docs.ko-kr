---
title: "isleadbyte, _isleadbyte_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_isleadbyte_l"
  - "isleadbyte"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_istleadbyte"
  - "_isleadbyte_l"
  - "isleadbyte"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "선행 바이트"
  - "_isleadbyte_l 함수"
  - "_istleadbyte 함수"
  - "istleadbyte 함수"
  - "isleadbyte 함수"
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# isleadbyte, _isleadbyte_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

문자가 멀티바이트 문자의 선행 바이트인지 여부를 결정합니다.  
  
> [!IMPORTANT]
>  이 API는 Windows 런타임에서 실행되는 응용 프로그램에서 사용할 수 없습니다. 자세한 내용은 [\/ZW에서 지원하지 않는 CRT 함수](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)를 참조하세요.  
  
## 구문  
  
```  
int isleadbyte(  
   int c   
);  
int _isleadbyte_l(  
   int c   
);  
```  
  
#### 매개 변수  
 `c`  
 테스트할 정수입니다.  
  
## 반환 값  
 `isleadbyte`는 인수가 테스트 조건을 만족할 경우 0이 아닌 값을 반환하고, 만족하지 않을 경우 0을 반환합니다. "C" 로캘 및 SBCS\(싱글바이트 문자 집합\) 로캘에서 `isleadbyte`는 항상 0을 반환합니다.  
  
## 설명  
 `isleadbyte` 매크로는 인수가 멀티바이트 문자의 첫 번째 바이트인 경우 0이 아닌 값을 반환합니다.`isleadbyte`는 –1\(`EOF`\)에서 `UCHAR_MAX`\(0xFF\)\(포함\) 사이의 모든 정수 인수에 대해 의미 있는 결과를 생성합니다.  
  
 `isleadbyte`의 예상 인수 형식은 `int`입니다. 부호 있는 문자가 전달되는 경우 컴파일러에서 부호 확장을 통해 정수로 변환하여 예측할 수 없는 결과를 생성할 수 있습니다.  
  
 `_l` 접미사가 있는 이 함수의 버전은 로캘 종속 동작에 현재 로캘 대신 전달된 로캘을 사용한다는 점을 제외하고는 동일합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_istleadbyte`|항상 false를 반환합니다.|**\_** `isleadbyte`|항상 false를 반환합니다.|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`isleadbyte`|\<ctype.h\>|  
|`_isleadbyte_l`|\<ctype.h\>|  
  
 호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 해당 .NET Framework 항목  
 적용할 수 없지만 [System::Globalization::CultureInfo](https://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.aspx)를 참조하세요.  
  
## 참고 항목  
 [바이트 분류](../../c-runtime-library/byte-classification.md)   
 [로캘](../../c-runtime-library/locale.md)   
 [\_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)
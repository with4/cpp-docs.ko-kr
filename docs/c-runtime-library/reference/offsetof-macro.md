---
title: "offsetof 매크로 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
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
apitype: "DLLExport"
f1_keywords: 
  - "offsetof"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "offsetof 매크로"
  - "구조체 멤버, 오프셋"
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# offsetof 매크로
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부모 구조의 시작 부분에서 멤버의 오프셋을 검색합니다.  
  
## 구문  
  
```  
  
        size_t offsetof(  
   structName,  
   memberName   
);  
```  
  
#### 매개 변수  
 *structName*  
 부모 데이터 구조의 이름입니다.  
  
 `memberName`  
 부모 데이터 구조에서 오프셋을 결정할 멤버의 이름입니다.  
  
## 반환 값  
 `offsetof`는 부모 데이터 구조에서 지정된 멤버의 오프셋\(바이트\)을 반환합니다.  이는 비트 필드의 경우 정의되지 않습니다.  
  
## 설명  
 `offsetof` 매크로는 *structName*에서 `size_t` 형식의 값으로 지정된 구조의 시작 부분에서 `memberName`의 오프셋\(바이트\)을 반환합니다.  `struct` 키워드로 형식을 지정할 수 있습니다.  
  
> [!NOTE]
>  `offsetof`는 함수가 아니며 C 프로토타입을 사용하여 설명할 수 없습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`offsetof`|\<stddef.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하세요.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 참고 항목  
 [메모리 할당](../../c-runtime-library/memory-allocation.md)
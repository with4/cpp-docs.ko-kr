---
title: "문자 할당 | Microsoft Docs"
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
helpviewer_keywords: 
  - "문자[C++], 할당"
  - "MBCS[C++], 문자 할당"
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# 문자 할당
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 예제는 `while` 루프에서 문자열을 검색하고 'X'를 제외한 모든 문자를 다른 문자열에 복사합니다.  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
        *sz1++ = *sz2++;  
    else  
        sz2++;  
}  
```  
  
 위 코드는 `sz2`의 바이트를 `sz1`이 가리키는 위치로 복사한 후 다음 바이트를 받기 위해 `sz1`을 증가시킵니다.  그러나 `sz2`의 다음 문자가 더블바이트 문자이면 `sz1`에 할당할 때 첫째 바이트만 복사됩니다.  다음 코드는 해당 문자를 안전하게 복사하는 이식 가능 함수와 `sz1`및 `sz2`를 제대로 증가시키는 다른 함수를 사용합니다.  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
    {  
        _mbscpy_s( sz1, 1, sz2 );  
        sz1 = _mbsinc( sz1 );  
        sz2 = _mbsinc( sz2 );  
    }  
    else  
        sz2 = _mbsinc( sz2 );  
}  
```  
  
## 참고 항목  
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)   
 [문자 비교](../text/character-comparison.md)
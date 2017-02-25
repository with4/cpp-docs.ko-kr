---
title: "버퍼 오버플로 | Microsoft Docs"
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
  - "버퍼 오버플로[C++]"
  - "버퍼[C++], 문자 크기"
  - "MBCS[C++], 버퍼 오버플로"
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# 버퍼 오버플로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문자 크기를 다르게 하면 문자를 버퍼에 넣을 때 문제가 발생할 수 있습니다.  예를 들어, 다음 코드는 `sz` 문자열의 문자를 `rgch`버퍼로 복사합니다.  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 복사된 마지막 바이트가 선행 바이트인 경우 문제가 발생합니다.  다음 코드는 버퍼를 오버플로할 수 있는 가능성이 있기 때문에 문제를 해결하지 못합니다.  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 `_mbccpy` 호출은 1바이트의 경우 및 2바이트의 경우 모두 전체 문자를 복사함으로써 올바로 작업을 수행하려고 합니다.  그러나 2바이트 문자의 경우 복사된 마지막 문자가 버퍼에 들어가지 않을 수 있다는 것을 고려하지 않습니다.  올바른 해결 방법은 다음과 같습니다.  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 위 코드는 `_mbclen`을 사용하여 `sz`가 가리키는 현재 문자 크기를 테스트함으로써 루프 테스트에서 가능한 버퍼 오버플로를 테스트합니다.  `_mbsnbcpy` 함수를 호출하여 `while` 루프의 코드를 한 줄로 바꿀 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## 참고 항목  
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)
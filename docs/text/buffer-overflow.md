---
title: 버퍼 오버플로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13d01460e7ed9cb95d92303d82ea136803737331
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854654"
---
# <a name="buffer-overflow"></a>버퍼 오버플로
문자 크기를 다르게 문자 버퍼에 배치할 때 문제가 발생할 수 있습니다. 문자열에서 문자를 복사, 다음 코드는 `sz`, 버퍼로 `rgch`:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 질문은: 마지막 바이트는 선행 바이트를 복사 했습니다. 다음 문제가 해결 되지 않는 버퍼를 오버플로될 수 때문에:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 `_mbccpy` 올바른 작업을 수행 하려면 호출 시도-1 개 또는 2 바이트 전체 문자를 복사 합니다. 하지만 문자가 2 바이트 이면 마지막 문자를 복사 버퍼에 들어가지 않을 수 있다는 것을 고려 하지 않습니다. 다음은 올바른 솔루션이입니다.  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 이 코드는 루프에서 가능한 버퍼 오버플로 대 한 테스트 사용 하 여 테스트 `_mbclen` 에서 가리키는 현재 문자 크기를 테스트 하려면 `sz`합니다. 호출 하 여는 `_mbsnbcpy` 함수에 코드를 대체할 수 있습니다는 `while` 코드 한 줄으로 루프입니다. 예를 들어:  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## <a name="see-also"></a>참고 항목  
 [MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)
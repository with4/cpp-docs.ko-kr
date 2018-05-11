---
title: 메시지 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- message_CPP
- vc-pragma.message
dev_langs:
- C++
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47b9fd580d1ebabf4352104fe49f1d3c982a49e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="message"></a>message
컴파일이 종료되지 않은 상태에서 문자열 리터럴을 표준 출력에 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#pragma message( messagestring )  
```  
  
## <a name="remarks"></a>설명  
 일반적인 용도 **메시지** pragma 컴파일 타임에 정보 메시지를 표시 하는 것입니다.  
  
 *messagestring* 매개 변수는 문자열 리터럴로 확장 되는 매크로 일 수 있으며 이러한 매크로 문자열 리터럴과 원하는 조합으로 연결할 수 있습니다.  
  
 미리 정의 된 매크로 사용 하는 경우는 **메시지** pragma 매크로 문자열을 반환 해야, 그렇지 않으면 매크로의 출력을 문자열로 변환 해야 합니다.  
  
 다음 코드 조각에서는 **메시지** pragma를 컴파일하는 동안 메시지를 표시 합니다.  
  
```  
// pragma_directives_message1.cpp  
// compile with: /LD  
#if _M_IX86 >= 500  
#pragma message("_M_IX86 >= 500")  
#endif  
  
#pragma message("")  
  
#pragma message( "Compiling " __FILE__ )   
#pragma message( "Last modified on " __TIMESTAMP__ )  
  
#pragma message("")  
  
// with line number  
#define STRING2(x) #x  
#define STRING(x) STRING2(x)  
  
#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")  
  
#pragma message("")  
```  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
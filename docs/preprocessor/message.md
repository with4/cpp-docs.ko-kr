---
title: "메시지 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fb998ef084f259601478ea9614a2bd8dc3da0d68
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
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
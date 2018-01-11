---
title: "마지막으로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dd357c8eeed9eddc6940ce02de6e5d2b4f8c68d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="finally"></a>finally
외에 `try` 및 `catch` 절, CLR 예외 지원 처리는 `finally` 절. 의미 체계와 동일는 `__finally` 구조적 예외 처리 (SEH)를 차단 합니다. A `__finally` 블록 따를 수는 `try` 또는 `catch` 블록입니다.  
  
## <a name="remarks"></a>설명  
 용도 `finally` 블록은 예외가 발생 한 후 남은 리소스를 정리할 수 있습니다. `finally` 예외가 throw 되지 않은 경우에 블록 없이 항상 실행 합니다. `catch` 블록은 관리 되는 예외가 throw 된 경우에 실행 됩니다 연결 된 `try` 블록입니다.  
  
 `finally`상황에 맞는 키워드입니다. 참조 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 간단한 `finally` 블록:  
  
```  
// keyword__finally.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyException: public System::Exception{};  
  
void ThrowMyException() {  
   throw gcnew MyException;  
}  
  
int main() {  
   try {  
      ThrowMyException();  
   }  
   catch ( MyException^ e ) {  
      Console::WriteLine(  "in catch" );  
      Console::WriteLine( e->GetType() );  
   }  
   finally {  
      Console::WriteLine(  "in finally" );  
   }  
}  
```  
  
```Output  
in catch  
MyException  
in finally  
```  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../windows/exception-handling-cpp-component-extensions.md)
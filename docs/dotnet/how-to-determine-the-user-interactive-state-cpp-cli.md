---
title: '방법: 사용자 대화형 상태 확인 (C + + /cli CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, user interactive state
- user interactive state
ms.assetid: 9f52323e-38b8-4a41-9b1d-052012ad839b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4649a6e7ce4833b55f38e636b87bb53f646e85cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127307"
---
# <a name="how-to-determine-the-user-interactive-state-ccli"></a>방법: 사용자 대화형 상태 확인(C++/CLI)
다음 코드 예제에서는 코드는 대화형 사용자 컨텍스트에서 실행 되는지 여부를 확인 하는 방법을 보여 줍니다. 경우 <xref:System.Environment.UserInteractive%2A> 가 false 이면는 코드가 실행 되는 서비스는 프로세스 또는에서 웹 응용 프로그램 내 경우 해서는 사용자와 상호 작용할 수 있습니다.  
  
## <a name="example"></a>예제  
  
```  
// user_interactive.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   if ( Environment::UserInteractive )  
      Console::WriteLine("User interactive");  
   else  
      Console::WriteLine("Noninteractive");  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [Windows 작업 (C + + /cli CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
---
title: '방법: 시작 후 경과한 시간 검색 (C + + /cli CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- time, elapsed since startup
- counters, elapsed time
- startup, time elapsed since
- tick counts
- startup
ms.assetid: a31fdecc-099e-4dd1-a176-f682289c5dd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4bebd086d24c741f0c5287e8a7fd0de6b535dfc6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-retrieve-time-elapsed-since-startup-ccli"></a>방법: 시작 후 경과한 시간 검색(C++/CLI)
Windows 이후 경과 된 시간 (밀리초)로 시작한 또는 다음 코드 예제에는 틱 수를 결정 하는 방법을 보여 줍니다. 이 값에 저장 되는 <xref:System.Environment.TickCount%2A?displayProperty=fullName> 멤버는 32 비트 값 이기 때문에 0으로 다시 설정은 및입니다.  
  
## <a name="example"></a>예제  
  
```  
// startup_time.cpp  
// compile with: /clr  
using namespace System;  
  
int main( )   
{  
   Int32 tc = Environment::TickCount;  
   Int32 seconds = tc / 1000;  
   Int32 minutes = seconds / 60;  
   float hours = static_cast<float>(minutes) / 60;  
   float days = hours / 24;  
  
   Console::WriteLine("Milliseconds since startup: {0}", tc);  
   Console::WriteLine("Seconds since startup: {0}", seconds);  
   Console::WriteLine("Minutes since startup: {0}", minutes);  
   Console::WriteLine("Hours since startup: {0}", hours);  
   Console::WriteLine("Days since startup: {0}", days);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [Windows 작업 (C + + /cli CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
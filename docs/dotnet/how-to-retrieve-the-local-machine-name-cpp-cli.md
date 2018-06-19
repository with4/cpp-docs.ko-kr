---
title: '방법: 로컬 컴퓨터 이름 검색 (C + + /cli CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- computer name, retrieving
- machine name, retrieving
- computer name
ms.assetid: 6c7acb9a-3f9b-43b2-a756-bd4fb859e697
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f02c9d12809ef908415c58c6b04da2597a3a1bfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33128643"
---
# <a name="how-to-retrieve-the-local-machine-name-ccli"></a>방법: 로컬 컴퓨터 이름 검색(C++/CLI)
다음 코드 예제에서는 로컬 컴퓨터 이름 검색 (네트워크에 표시 되는 컴퓨터의 이름). 가져와서이 수행할 수 있습니다는 <xref:System.Environment.MachineName%2A> 문자열에서 정의 되는 <xref:System.Environment> 네임 스페이스입니다.  
  
## <a name="example"></a>예제  
  
```  
// machine_name.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nMachineName: {0}", Environment::MachineName);  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [Windows 작업 (C + + /cli CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
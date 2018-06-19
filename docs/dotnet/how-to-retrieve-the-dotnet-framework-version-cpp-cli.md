---
title: 방법:.NET Framework 버전 검색 (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- .NET Framework, version
- Version property, retrieving .NET Framework version
ms.assetid: fc786fbc-c915-4b15-bcad-0d68cf2c44bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f8bc471cda452bd387478a75dd047631c0359ed1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33128773"
---
# <a name="how-to-retrieve-the-net-framework-version-ccli"></a>방법: .NET Framework 버전 검색(C++/CLI)
다음 코드 예제는 현재 설치 된.NET Framework의 버전을 확인 하는 방법을 보여 줍니다는 <xref:System.Environment.Version%2A> 포인터 속성에는 <xref:System.Version> 버전 정보를 포함 하는 개체입니다.  
  
## <a name="example"></a>예제  
  
```  
// dotnet_ver.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   Version^ version = Environment::Version;  
   if (version)  
   {  
      int build = version->Build;  
      int major = version->Major;  
      int minor = version->Minor;  
      int revision = Environment::Version->Revision;  
      Console::Write(".NET Framework version: ");  
      Console::WriteLine("{0}.{1}.{2}.{3}",   
            build, major, minor, revision);  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [Windows 작업 (C + + /cli CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
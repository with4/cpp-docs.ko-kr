---
title: "ADO.NET를 사용 하 여 데이터 액세스 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ADO.NET [C++]
- .NET Framework [C++], data access
- databases [C++], accessing in C++
- data access [C++], ADO.NET
- data [C++], ADO.NET
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f243b18b2666c21a6d83eabe35ecd6ad9df5905c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="data-access-using-adonet-ccli"></a>ADO.NET을 사용하여 데이터 액세스(C++/CLI)
ADO.NET은 데이터 액세스를 위한.NET Framework API 및 성능과 이전 데이터 액세스 솔루션에서 일치 하지 않는 사용 편의성을 제공 합니다. 이 섹션에 네이티브 형식을 마샬링하 등의 Visual c + + 사용자 고유의 ADO.NET 관련 문제 중 일부를 설명 합니다.  
  
 ADO.NET에는 공용 언어 런타임 (CLR)에서 실행 됩니다. 따라서 ADO.NET 상호 작용 하는 모든 응용 프로그램은 CLR를 대상도 해야 합니다. 그러나 의미는 아닙니다 네이티브 응용 프로그램 ADO.NET을 사용할 수 없습니다. 이 예제에서는 네이티브 코드에서 ADO.NET 데이터베이스와 상호 작용 하는 방법을 보여 줍니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [방법: ADO.NET용 ANSI 문자열 마샬링(C++/CLI)](../dotnet/how-to-marshal-ansi-strings-for-adonet-cpp-cli.md)  
  
 [방법: ADO.NET용 BSTR 문자열 마샬링(C++/CLI)](../dotnet/how-to-marshal-bstr-strings-for-adonet-cpp-cli.md)  
  
 [방법: ADO.NET용 유니코드 문자열 마샬링(C++/CLI)](../dotnet/how-to-marshal-unicode-strings-for-adonet-cpp-cli.md)  
  
 [방법: ADO.NET용 VARIANT 마샬링(C++/CLI)](../dotnet/how-to-marshal-a-variant-for-adonet-cpp-cli.md)  
  
 [방법: ADO.NET용 SAFEARRAY 마샬링(C++/CLI)](../dotnet/how-to-marshal-a-safearray-for-adonet-cpp-cli.md)  
  
## <a name="related-sections"></a>관련 단원  
  
|단원|설명|  
|-------------|-----------------|  
|[ADO.NET](/dotnet/framework/data/adonet/index)|ADO.NET에는.NET 프로그래머에 게 데이터 액세스 서비스를 노출 하는 클래스 집합에 대 한 개요를 제공 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [.NET 프로그래밍 C + + /cli CLI (Visual c + +)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)
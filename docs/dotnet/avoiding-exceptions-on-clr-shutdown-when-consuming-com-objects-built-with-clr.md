---
title: -Clr과 빌드한 COM 개체에서 발생 한 예외를 방지 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0efd2af7eb4bf8a70bff983d627f802f1976c6ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>/clr로 빌드한 COM 개체를 사용할 때 CLR 종료 시 예외 방지
공용 언어 런타임 (CLR) 종료 모드로 설정 되 면 네이티브 함수를 CLR 서비스에 대 한 액세스를 제한 됩니다. COM 개체를 사용 하 여 컴파일된에서 릴리스를 호출 하려고 할 때 **/clr**, 네이티브 코드에 CLR 전환 되 고 다음 관리 코드에 서비스 (관리 코드에서 정의 됨)는 iunknown:: Release 호출으로 다시 전환 합니다. CLR 종료 모드 이므로 관리 코드로 다시 호출을 방지 합니다.  
  
 이 문제를 해결 하려면 릴리스 메서드에서 호출 된 소멸자에만 네이티브 코드가 들어를 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)
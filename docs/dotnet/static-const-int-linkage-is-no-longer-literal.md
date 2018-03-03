---
title: "Static Const Int 링크가 더 이상 리터럴 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- literal attribute [C++]
- constants, declaring
- integral constant expressions
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8f34682fa780ef430d27104d3df9658f9e32ad39
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="static-const-int-linkage-is-no-longer-literal"></a>Static Const Int 링크가 더 이상 리터럴이 아닙니다.
상수 멤버 클래스의 선언 Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 하지만 `static const` 정수 계열 멤버가 여전히 지원 되는 경우 해당 링크 특성이 변경 되었습니다. 이제 이전 링크 특성은 정수 리터럴 멤버에서 수행 됩니다. 예를 들어 다음 Managed Extensions 클래스를 살펴보세요.  
  
```  
public __gc class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 이 필드 (참고 리터럴 특성)에 대 한 다음과 같은 기본 CIL 특성에서는 생성 됩니다.  
  
```  
.field public static literal int32   
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 하지만 여전히 새 구문에서 컴파일합니다.  
  
```  
public ref class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 리터럴 특성을 더 이상 생성 하 고 따라서 인식 되지 않습니다는 상수로 CLR 런타임에서 합니다.  
  
```  
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 같은 언어 간 리터럴 특성을 가지려면 선언을 변경 해야 새로 지원 되 `literal` 다음과 같이 데이터 멤버  
  
```  
public ref class Constants {  
public:  
   literal int LOG_DEBUG = 4;  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스 또는 인터페이스 내에서 멤버 선언 (C + + /cli CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [리터럴](../windows/literal-cpp-component-extensions.md)
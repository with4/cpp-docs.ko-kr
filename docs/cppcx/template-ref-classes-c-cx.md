---
title: "템플릿 ref 클래스 (C + + /cli CX) | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
caps.latest.revision: "15"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 91e039f3154d7b459e3bde9804604218b5ce1c4d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="template-ref-classes-ccx"></a>템플릿 ref 클래스(C++/CX)
C++ 템플릿은 메타데이터에 게시되지 않으므로 프로그램에서 public 또는 protected 액세스 가능성을 가질 수 없습니다. 물론 표준 C++ 템플릿을 프로그램에서 내부적으로 사용할 수 있습니다. 또한 private ref 클래스를 템플릿으로 정의하고 명시적으로 특수화된 템플릿 ref 클래스를 public ref 클래스에서 private 멤버로 선언할 수 있습니다.  
  
## <a name="authoring-ref-class-templates"></a>ref 클래스 템플릿 작성  
 다음 예제에서는 private ref 클래스를 템플릿으로 선언하는 방법 및 표준 C++ 템플릿을 선언하는 방법과 이 둘을 public ref 클래스에서 멤버로 선언하는 방법을 보여 줍니다. 표준 c + + 템플릿을이 Windows 런타임 형식으로 특수화 될 수 있습니다 참고 경우는 platform:: string ^ 합니다.  
  
 [!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]  
  
## <a name="see-also"></a>참고 항목  
 [형식 시스템(C++/CX)](../cppcx/type-system-c-cx.md)   
 [Visual c + + 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)   
 [네임 스페이스 참조](../cppcx/namespaces-reference-c-cx.md)
---
title: "Override 지정자 (c + + 구성 요소 확장명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- override specifiers, Visual C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7937e0eec53a800c7bcef2842310af368949bcca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="override-specifiers--c-component-extensions"></a>Override 지정자(C++ 구성 요소 확장)
*Override 지정자* 방법을 수정 하 고 상속 된 형식의 멤버가 파생된 형식에서 작동 합니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 **주의**  
  
 재정의 지정자에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [new (의 new 슬롯 vtable)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   [재정의 지정자 및 네이티브 컴파일](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)  
  
 재정의 지정자로 사용되지 않는 형식 선언에서는 `abstract` 및 `sealed`도 유효합니다.  
  
 기본 클래스 함수를 명시적으로 재정의 하는 방법에 대 한 정보를 참조 하십시오. [명시적으로 재정의](../windows/explicit-overrides-cpp-component-extensions.md)합니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
 (이 언어 기능에는 Windows 런타임에만 적용되는 설명이 없습니다.)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임  
 (이 언어 기능에는 공용 언어 런타임에만 적용되는 설명이 없습니다.)  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)
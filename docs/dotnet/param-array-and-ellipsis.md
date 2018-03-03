---
title: "매개 변수 배열 및 줄임표 | Microsoft Docs"
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
- function overloading, argument matching
ms.assetid: 492e3f6c-1c4c-4e0c-a358-72f2d39c30be
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f6d256fd48d8c9f206619e6baa9a50a0278d30c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="param-array-and-ellipsis"></a>매개 변수 배열 및 가변 매개 변수(...)
오버 로드 된 함수 호출을 확인 하는 것에 대 한 매개 변수 배열의 우선 순위 Visual c + + Managed Extensions for c + + 변경 되었습니다.  
  
 Managed Extensions 및 새 구문에서 지 원하는 C# 및 Visual Basic 매개 변수 배열에 대 한 지원이 있습니다. 대신 플래그 하나 특성을 사용 하 여 일반 배열을 다음과 같습니다.  
  
```  
void Trace1( String* format, [ParamArray]Object* args[] );  
void Trace2( String* format, Object* args[] );  
```  
  
 이 둘은 모두 동일 하 게 보이지만 동안는 `ParamArray` 특성 태그를 삽입이 C# 이나 다른 CLR 언어에 대 한 각 호출 마다 요소 변수 번호를 가져오는 배열입니다. 관리 되는 확장 및 새 구문 간에 프로그램에서 동작의 변화에 줄임표를 선언 하는 한 인스턴스를 설정 하는 오버 로드 된 함수를 확인에 있고 두 번째 선언 된 `ParamArray` 제공한 다음 예제와 같이 특성 Artur Laksberg 합니다.  
  
```  
int fx(...); // 1  
int fx( [ParamArray] Int32[] ); // 2  
```  
  
 Managed extensions에서 줄임표 특성은 아니므로 언어의 정식 측면은 부적절 하는 특성을 통해 우선 순위를 제공 되었습니다. 그러나 새 구문에서 매개 변수 배열 언어에서 내에서 직접 사용할 수 이제 있으며는 더 강력한 형식 때문에 가변 매개 변수를 통해 보다 우선 순위가 높습니다. Managed Extensions로 설정 하는 호출에 따라서,  
  
```  
fx( 1, 2 );  
```  
  
 확인 `fx(...)` 확인 되는 새 구문에서는 `ParamArray` 인스턴스. 에 프로그램 동작이 아닌 줄임표 인스턴스의 호출에 따라 달라 지는 `ParamArray`, 서명 또는 호출 중 하나를 수정 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [일반적인 언어 변경 사항(C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)
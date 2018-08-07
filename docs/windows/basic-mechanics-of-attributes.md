---
title: 특성의 기본 메커니즘 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], inserting in code
- attributes [C++], about attributes
ms.assetid: dc2069c3-b9f3-4a72-965c-4e5208ce8e34
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3bb7ff68f9c17f7b90261c2c96630911454842a5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462494"
---
# <a name="basic-mechanics-of-attributes"></a>특성의 기본 메커니즘
프로젝트에 특성을 삽입 하는 방법은 세 가지가 있습니다. 첫째, 삽입할 수 있습니다 이러한 수동으로 소스 코드입니다. 둘째,이 프로젝트에서 개체의 속성 표를 사용 하 여 삽입할 수 있습니다. 마지막으로, 다양 한 마법사를 사용 하 여 삽입할 수 있습니다. 사용 하 여 대 한 자세한 내용은 합니다 **속성** 창 및 다양 한 마법사를 참조 하십시오 [Creating and Managing Visual c + + Projects](../ide/creating-and-managing-visual-cpp-projects.md)합니다.  
  
 로 이전에 프로젝트를 빌드할 때 컴파일러 구문 분석 각 c + + 소스 파일을 개체 파일을 생성 합니다. 그러나 컴파일러는 특성을 발견 하면 해당 구문 분석 되 고 구문적으로 확인 합니다. 컴파일러가 다음 동적으로 공급자를 호출할 특성 코드를 삽입 하거나 컴파일 타임에 기타 수정 작업을 확인 합니다. 공급자 구현 형식 특성에 따라 다릅니다. 예를 들어, ATL 관련 특성 Atlprov.dll 여 구현 됩니다.  
  
 다음 그림에서는 컴파일러 및 특성 공급자 간의 관계를 보여 줍니다.  
  
 ![구성 요소 특성 통신](../windows/media/vccompattrcomm.gif "vcCompAttrComm")  
  
> [!NOTE]
>  특성 사용 소스 파일의 내용을 변경 하지 않습니다. 디버깅 세션 중에 생성 된 특성 코드를 표시 됩니다. 또한 프로젝트의 각 소스 파일에 대 한 특성 대체의 결과 표시 하는 텍스트 파일을 생성할 수 있습니다. 이 절차에 대 한 자세한 내용은 참조 하세요. [/Fx (삽입 된 코드 병합)](../build/reference/fx-merge-injected-code.md) 하 고 [삽입 된 코드 디버그](/visualstudio/debugger/how-to-debug-injected-code)합니다.  
  
 대부분의 c + + 구문에 같은 특성에는 적절 한 용도 정의 하는 특성 집합입니다. 이 특성의 컨텍스트로 라고 하 고는 각 특성 참조 항목에 대 한 특성 상황에 맞는 테이블에서 처리 됩니다. 예를 들어 합니다 [coclass](../windows/coclass.md) 특성 수와 반대로 기존 클래스 또는 구조체에 적용 하는 수는 [cpp_quote](../windows/cpp-quote.md) 특성을 c + + 소스 파일 내의 아무 곳 이나 삽입할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../windows/attributed-programming-concepts.md)
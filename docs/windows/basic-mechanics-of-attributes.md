---
title: "특성의 기본 메커니즘 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- attributes [C++], inserting in code
- attributes [C++], about attributes
ms.assetid: dc2069c3-b9f3-4a72-965c-4e5208ce8e34
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99771e798e4957de5ff69601a5d3494e5fcacc35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="basic-mechanics-of-attributes"></a>특성의 기본 메커니즘
프로젝트에 특성을 삽입 하는 방법은 세 가지가 있습니다. 첫째, 삽입할 수 있습니다 수동으로 소스 코드에 있습니다. 둘째, 프로젝트에서 개체의 속성 표를 사용 하 여 삽입할 수 있습니다. 마지막으로, 다양 한 마법사를 사용 하 여 삽입할 수 있습니다. 속성 창 및 다양 한 마법사 사용에 대 한 자세한 내용은 참조 하십시오. [만들기 및 Visual c + + 프로젝트 관리](../ide/creating-and-managing-visual-cpp-projects.md)합니다.  
  
 으로 이전에 프로젝트를 빌드할 때 컴파일러 구문 분석 하 여 개체 파일의 각 c + + 소스 파일. 그러나 컴파일러 특성을 발견 하면 구문 분석 이며 구문상 확인 합니다. 컴파일러 다음 동적으로 호출 하 여 특성 공급자 코드를 삽입 하거나 다른 수정 사항 컴파일 타임에 확인 합니다. 공급자의 구현 특성 유형에 따라 달라 집니다. 예를 들어 Atlprov.dll ATL 관련 특성을 구현 합니다.  
  
 다음 그림에서는 컴파일러가 특성 공급자와의 관계를 보여 줍니다.  
  
 ![구성 요소 특성 통신](../windows/media/vccompattrcomm.gif "vcCompAttrComm")  
  
> [!NOTE]
>  특성 사용 소스 파일의 내용을 변경 하지 않습니다. 디버깅 세션 중에 표시 되는 생성 된 특성 코드입니다. 또한 프로젝트의 각 소스 파일에 대 한 특성 대체의 결과 표시 하는 텍스트 파일을 생성할 수 있습니다. 이 절차에 대 한 자세한 내용은 참조 하십시오. [/Fx (삽입 된 코드 병합)](../build/reference/fx-merge-injected-code.md) 및 [삽입 된 코드 디버그](/visualstudio/debugger/how-to-debug-injected-code)합니다.  
  
 대부분의 c + + 구문을 처럼 특성 집합을 적절 한 용도 정의 하는 특성이 있습니다. 이 특성의 컨텍스트 라고 하 고는 각 특성 참조 항목에 대 한 특성 컨텍스트 테이블에서 처리 됩니다. 예를 들어는 [coclass](../windows/coclass.md) 특성 수 반대인만 기존 클래스 또는 구조에 적용 하는 수는 [cpp_quote](../windows/cpp-quote.md) 특성을 c + + 소스 파일 내의 임의의 위치에 삽입할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../windows/attributed-programming-concepts.md)
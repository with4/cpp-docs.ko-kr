---
title: 추가 속성 (Visual c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding properties
- properties [C++], adding to interfaces
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45eda098202fdf9286905bdc967b6aa1d7bd7035
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="adding-a-property-visual-c"></a>속성 추가(Visual C++)
사용할 수는 [속성 추가 마법사](../ide/names-add-property-wizard.md) 프로젝트에는 인터페이스 메서드를 추가 하 합니다.  
  
### <a name="to-add-a-property-to-your-object"></a>개체에 속성을 추가 하려면  
  
1.  [클래스 뷰](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), 속성을 추가 하려면 원하는 인터페이스의 이름을 마우스 오른쪽 단추로 클릭 합니다.  
  
    > [!NOTE]
    >  Dispinterface 프로젝트 특성을 사용 하지 않으면 라이브러리 노드 내에 중첩 된에 속성을 추가할 수도 있습니다.  
  
2.  바로 가기 메뉴에서 클릭 **추가**, 클릭 하 고 **속성 추가**합니다.  
  
3.  에 [속성 추가 마법사](../ide/names-add-property-wizard.md), 속성을 만드는 데 필요한 정보를 제공 합니다.  
  
4.  에 있는 속성에 대 한 인터페이스 정의 (IDL) 언어 설정을 지정는 [IDL 특성](../ide/idl-attributes-add-property-wizard.md) 마법사의 페이지입니다.  
  
5.  클릭 **마침** 는 속성을 추가 합니다.  
  
 **가져오기** 및 `Put` 속성의 메서드가 정의 된 인터페이스 클래스 뷰에서 두 개의 아이콘으로 표시 됩니다. .Idl 파일에서 속성 선언을 볼 아이콘 중 하나를 두 번 클릭 수 있습니다.  
  
-   ATL 인터페이스는 **가져오기** 및 **배치** 함수.cpp 파일에 추가 되 고 이러한 함수에 대 한 참조.h 파일에 추가 됩니다.  
  
-   선택 하는 경우 MFC dispinterface에 대 한 **멤버 변수** 구현 하는 클래스에는 메서드 및 변수를 구현 형식으로 추가 합니다. 선택 하는 경우 **Get/Set 메서드** 구현 형식으로 두 가지 방법을 구현 하는 클래스에 추가 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [COM 인터페이스 만들기](../ide/creating-a-com-interface-visual-cpp.md)   
 [COM 인터페이스 편집](../ide/editing-a-com-interface.md)   
 [구성 요소 개체 모델](http://msdn.microsoft.com/library/windows/desktop/ms694363)   
 [인터페이스 포인터 및 인터페이스](http://msdn.microsoft.com/library/windows/desktop/ms688484)
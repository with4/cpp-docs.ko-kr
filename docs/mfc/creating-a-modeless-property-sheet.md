---
title: "모덜리스 속성 시트 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- modeless property sheets
- property sheets, modeless
- Create method [MFC], property sheets
ms.assetid: eafd8a92-cc67-4a69-a5fb-742c920d1ae8
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2e587c130a06ff30a38138f1e0ecf94e7cdfe1ad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-modeless-property-sheet"></a>모덜리스 속성 시트 만들기
일반적으로 만들어야 하는 속성 시트 모달 됩니다. 모달 속성 시트를 사용 하는 경우 사용자는 응용 프로그램의 다른 부분을 사용 하기 전에 속성 시트를 닫아야 합니다. 이 문서에 사용자를 응용 프로그램의 다른 부분을 사용 하는 동안 속성 시트를 열어 모덜리스 속성 시트를 만드는 데 사용할 수 있는 방법을 설명 합니다.  
  
 속성 시트 모달 대화 상자로 대신 모덜리스 대화 상자를 표시 하려면 호출 [CPropertySheet::Create](../mfc/reference/cpropertysheet-class.md#create) 대신 [DoModal](../mfc/reference/cpropertysheet-class.md#domodal)합니다. 모덜리스 속성 시트를 지원 하기 위해 몇 가지 추가 작업을 구현 해야 합니다.  
  
 속성 시트 및 속성 시트 열릴 때 수정 외부 개체 간에 데이터를 교환할 때 추가 작업 중 하나입니다. 일반적으로 표준 모덜리스 대화 상자와 같은 작업입니다. 이 작업의 일부로 모덜리스 속성 시트 및 속성 설정이 적용 되는 외부 개체 간의 통신 채널을 구현 합니다. 이 구현은에서 클래스를 파생 하는 경우 훨씬 더 쉽습니다 [CPropertySheet](../mfc/reference/cpropertysheet-class.md) 모덜리스 속성 시트에 대 한 합니다. 이 문서에서는 그렇게 않은 가정 합니다.  
  
 모덜리스 속성 시트에서 외부와 통신 하기 위한 한 가지 방법은 외부 개체에 속성 시트에서 포인터를 정의 하는 개체 (예: 보기에서 현재 선택). 함수 정의 (다음과 같이 호출 `SetMyExternalObject`)에 `CPropertySheet`-다른 하나의 외부 개체에서 포커스가 변경 될 때마다 포인터를 변경 하는 클래스를 파생 합니다. `SetMyExternalObject` 함수가 새로 선택 된 외부 개체를 반영 하기 위해 각 속성 페이지에 대 한 설정을 다시 설정 해야 합니다. 이 수행 하는 `SetMyExternalObject` 함수에 액세스할 수 있어야는 [CPropertyPage](../mfc/reference/cpropertypage-class.md) 에 속하는 개체는 `CPropertySheet` 클래스입니다.  
  
 포함 하는 속성 시트 내부에서 속성 페이지에 대 한 액세스를 제공 하는 가장 편리한 방법은 `CPropertyPage` 개체에 `CPropertySheet`-파생 된 개체입니다. 포함 `CPropertyPage` 개체에 `CPropertySheet`-모달 대화 상자, 속성 시트의 소유자를 만들어 위치에 대 한 일반적인 디자인에서 파생 된 개체와 다른는 `CPropertyPage` 개체 및이를 통해 속성 시트에 전달 [ CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage)합니다.  
  
 모덜리스 속성 시트의 설정의 외부 개체에 적용 해야 하는 시기를 결정 하기 위한 많은 사용자 인터페이스 대체 방법이 있습니다. 한 가지 대안은 사용자 모든 값이 변경 될 때마다 현재 속성 페이지의 설정을 적용 하는 것입니다. 또 다른 방법은 적용 단추를 사용 하면 속성 페이지에서 변경 내용을 외부 개체에 커밋하기 전에 누적를 제공 하는 것입니다. 적용 단추 처리 하는 방법에 대 한 자세한 내용은 문서 참조 [적용 단추 처리](../mfc/handling-the-apply-button.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 시트](../mfc/property-sheets-mfc.md)   
 [데이터 교환](../mfc/exchanging-data.md)   
 [대화 상자의 수명 주기](../mfc/life-cycle-of-a-dialog-box.md)


---
title: "적용 단추 처리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Apply button in property sheet
- property sheets, Apply button
ms.assetid: 7e977015-59b8-406f-b545-aad0bfd8d55b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d72186d3b3d29613007291396aa07ba4060a726a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="handling-the-apply-button"></a>적용 단추 처리
속성 시트에는 기능이 없는 표준 대화 상자: 속성 시트를 닫기 전에 변경한 내용을 적용 하려면 사용자를 허용 합니다. 이 작업은 수행 [적용] 단추를 사용 하 여 합니다. 이 문서에서는이 기능을 제대로 구현 하는 데 사용할 수 하는 방법을 설명 합니다.  
  
 모달 대화 상자를 일반적으로 설정을 적용 외부 개체에 사용자가 대화 상자를 닫으려면 확인을 클릭 합니다. 속성 시트에도 마찬가지입니다: 속성 시트에서 새 설정을 적용 하려면 사용자가 확인을 클릭 하는 경우.  
  
 그러나 다음 사용자 속성 시트 대화 상자를 종료 하지 않고 설정을 저장 하도록 허용 하는 것이 좋습니다. 적용 단추 함수입니다. 적용 단추에는 외부 개체에만 현재 사용 중인 페이지의 현재 설정을 적용 하는 대신에 모든 속성 페이지의 현재 설정을 적용 됩니다.  
  
 기본적으로 적용 단추는 항상 사용 하지 않도록 설정 합니다. 적절 한 시간에 [적용] 단추를 사용 하도록 설정 하려면 코드를 작성 해야 하 고 아래에 설명 된 대로 적용의 효과 구현 하는 코드를 작성 해야 합니다.  
  
 사용자에 게 적용 기능을 제공 하려면 [적용] 단추를 제거할 필요는 없습니다. 내용이 Windows 향후 버전에서 사용할 수 있는 표준 속성 시트 지원을 사용 하는 응용 프로그램 간에 공통적으로 적용 되므로 사용 하지 않도록 둘 수 있습니다.  
  
 수정 중인으로 페이지를 고 [적용] 단추를 사용 하도록 설정 하려면 호출 **CPropertyPage::SetModified (TRUE)**합니다. 보고 수정 하 고 있는 경우 [적용] 단추 현재 활성 페이지의 수정 여부에 관계 없이 사용 가능한 상태로 유지 됩니다.  
  
 호출 해야 [CPropertyPage::SetModified](../mfc/reference/cpropertypage-class.md#setmodified) 사용자 페이지의 설정을 변경 될 때마다 합니다. 와 같은 각 속성 페이지에 있는 컨트롤에 대 한 변경 알림 처리기를 구현 하는 사용자 페이지에 있는 설정을 변경 하는 시기를 감지 하는 한 가지 방법은 **EN_CHANGE** 또는 **BN_CLICKED**합니다.  
  
 적용 단추의 효과 구현 하려면 속성 시트가 소유자 또는 기타 외부 개체가 속성 페이지의 현재 설정을 적용 하려면 응용 프로그램에 지시 해야 합니다. 같은 시간에 속성 시트 사용 하지 않도록 적용 단추를 호출 하 여 **CPropertyPage::SetModified (FALSE)** 외부 개체에 해당 수정 내용을 적용 하는 모든 페이지에 대 한 합니다.  
  
 이 프로세스의 예를 들어 MFC 일반 샘플을 참조 하십시오. [PROPDLG](../visual-cpp-samples.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 시트](../mfc/property-sheets-mfc.md)


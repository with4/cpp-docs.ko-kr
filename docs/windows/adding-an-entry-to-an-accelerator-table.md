---
title: "액셀러레이터 키 테이블에 항목 추가 | Microsoft Docs"
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
- accelerator tables [C++], adding entries
- New Accelerator command
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9fe2df81aae0b9b7232443de1db091a9cbb0c0d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-entry-to-an-accelerator-table"></a>액셀러레이터 키 테이블에 항목 추가
### <a name="to-add-an-entry-to-an-accelerator-table"></a>액셀러레이터 키 테이블에 항목을 추가하려면  
  
1.  액셀러레이터 키 테이블에서 해당 아이콘을 두 번 클릭 하 여 열고 [리소스 뷰](../windows/resource-view-window.md)합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  액셀러레이터 키 테이블 내에서 마우스 오른쪽 단추로 클릭 하 고 선택 **새 액셀러레이터 키** 바로 가기 메뉴 또는 테이블의 맨 아래에 빈 행 항목을 클릭 합니다.  
  
3.  선택 된 [ID](id-property.md) ID에서 드롭 다운 목록에서 상자에 새 ID를 입력 또는 **ID** 상자입니다.  
  
4.  형식은 [키](../windows/accelerator-key-property.md) 액셀러레이터 키 또는 마우스 오른쪽 단추 클릭으로 사용 하 고 선택 하려면 **다음 입력 된 키** 키 조합을 설정 하려면 바로 가기 메뉴에서 (의 **다음 입력 된 키** 명령은 사용할 수 있는 **편집** 메뉴).  
  
5.  변경 된 [한정자](../windows/accelerator-modifier-property.md) 및 [형식](../windows/accelerator-type-property.md)필요한 경우.  
  
6.  **ENTER** 키를 누릅니다.  
  
    > [!NOTE]
    >  정의한 모든 액셀러레이터 키가 고유한지 확인합니다. 여러 키 조합이 동일한 ID에 할당될 수 있으며 잘못된 영향을 주지 않습니다. 예를 들어 Ctrl+P와 F8 키가 둘 다 ID_PRINT에 할당될 수 있습니다. 그러나 키 조합이 둘 이상의 ID에 할당되면 제대로 작동하지 않습니다. 예를 들어 Ctrl+Z가 ID_SPELL_CHECK와 ID_THESAURUS 모두에 할당됩니다.  
  

  
 **요구 사항**  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키 테이블 편집](../windows/editing-accelerator-tables.md)   
 [액셀러레이터 키 편집기](../windows/accelerator-editor.md)
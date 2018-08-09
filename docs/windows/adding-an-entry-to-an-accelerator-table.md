---
title: 액셀러레이터 키 테이블에 항목 추가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], adding entries
- New Accelerator command
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e0c5e94913a705ac97407f82075ff9c83a12dd6b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642791"
---
# <a name="adding-an-entry-to-an-accelerator-table"></a>액셀러레이터 키 테이블에 항목 추가
### <a name="to-add-an-entry-to-an-accelerator-table"></a>액셀러레이터 키 테이블에 항목을 추가하려면  
  
1.  액셀러레이터 키 테이블에서 해당 아이콘을 두 번 클릭 하 여 [리소스 뷰](../windows/resource-view-window.md)합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  액셀러레이터 키 테이블 내에서 마우스 오른쪽 단추로 클릭 하 고 선택 **새 액셀러레이터 키** 바로 가기 메뉴에서 테이블의 맨 아래에 빈 행 항목을 클릭 합니다.  
  
3.  선택는 [ID](id-property.md) ID 드롭다운 목록에서 상자 또는에 새 ID를 입력 합니다 **ID** 상자.  
  
4.  형식 합니다 [키](../windows/accelerator-key-property.md) 액셀러레이터 키 또는 마우스 오른쪽 단추 클릭으로 사용 하 고 선택 하려는 **다음 입력 된 키** 키 조합을 설정 하려면 바로 가기 메뉴에서 (합니다 **다음 입력 된 키** 명령입니다 에서도 사용 가능 합니다 **편집** 메뉴).  
  
5.  변경 된 [한정자](../windows/accelerator-modifier-property.md) 하 고 [형식](../windows/accelerator-type-property.md)필요한 경우.  
  
6.  **ENTER** 키를 누릅니다.  
  
    > [!NOTE]
    >  정의한 모든 액셀러레이터 키가 고유한지 확인합니다. 예를 들어 잘못 된 없습니다 효과가 적용 된 동일한 ID를 할당 하는 여러 키 조합이 할 수 있습니다 **Ctrl** + **P** 하 고 **F8** 둘 다 ID_PRINT에 할당 될 수 있습니다. 그러나 둘 이상의 ID 제대로 작동 하지 것입니다, 예를 들어 할당할 키 조합을 것 **Ctrl** + **Z** 가 ID_SPELL_CHECK와 ID_THESAURUS 모두에 할당 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키 테이블 편집](../windows/editing-accelerator-tables.md)   
 [액셀러레이터 키 편집기](../windows/accelerator-editor.md)
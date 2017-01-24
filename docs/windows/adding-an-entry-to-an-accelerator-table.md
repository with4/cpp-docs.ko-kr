---
title: "액셀러레이터 키 테이블에 항목 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "항목 추가 액셀러레이터 키 테이블 [c + +]"
  - "새 액셀러레이터 키 명령"
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 액셀러레이터 키 테이블에 항목 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### <a name="to-add-an-entry-to-an-accelerator-table"></a>액셀러레이터 키 테이블에 항목을 추가하려면  
  
1.  액셀러레이터 키 테이블에서 해당 아이콘을 두 번 클릭 하 여 [리소스 뷰](../windows/resource-view-window.md)합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  액셀러레이터 키 테이블 내에서 마우스 오른쪽 단추로 클릭 하 고 선택 **새 액셀러레이터 키** 바로 가기 메뉴 또는 테이블의 맨 아래에 빈 행 항목을 클릭 합니다.  
  
3.  선택 된 [ID](Id%20Property.xml) ID 드롭다운 목록에서 상자에 새 ID를 입력 하거나는 **ID** 상자입니다.  
  
4.  형식은 [키](../windows/accelerator-key-property.md) 액셀러레이터 키 또는 마우스 오른쪽 단추 클릭으로 사용 하 고 선택 하려면 **다음 입력 된 키** 키 조합을 설정 하려면 바로 가기 메뉴에서 (의 **다음 입력 된 키** 명령에서 제공 됩니다.는 **편집** 메뉴).  
  
5.  변경 된 [한정자](../windows/accelerator-modifier-property.md) 및 [형식](../windows/accelerator-type-property.md), 필요한 경우.  
  
6.  키를 눌러 **ENTER**합니다.  
  
    > [!NOTE]
    >  정의한 모든 액셀러레이터 키가 고유한지 확인합니다. 여러 키 조합이 동일한 ID에 할당될 수 있으며 잘못된 영향을 주지 않습니다. 예를 들어 Ctrl+P와 F8 키가 둘 다 ID_PRINT에 할당될 수 있습니다. 그러나 키 조합이 둘 이상의 ID에 할당되면 제대로 작동하지 않습니다. 예를 들어 Ctrl+Z가 ID_SPELL_CHECK와 ID_THESAURUS 모두에 할당됩니다.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 [.NET Framework 개발자 가이드](../Topic/Resources%20in%20Desktop%20Apps.md) 에서 *응용 프로그램의 리소스* 를 참조하세요합니다. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP합니다.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)합니다.  
  
 **Requirements**  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [액셀러레이터 키 테이블 편집](../windows/editing-accelerator-tables.md)   
 [액셀러레이터 키 편집기](../mfc/accelerator-editor.md)
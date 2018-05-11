---
title: '방법: 리소스 스크립트 파일에 MFC 지원을 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.add.MFC
dev_langs:
- C++
helpviewer_keywords:
- rc files, adding MFC support
- .rc files, adding MFC support
- MFC, adding support to resource scripts files
- resource script files, adding MFC support
ms.assetid: 599dfe9d-ad26-4e34-899c-49b56599e37f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 50c0493e630c2b141da1fced6964ffc514c761d4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-add-mfc-support-to-resource-script-files"></a>방법: 리소스 스크립트 파일에 MFC 지원 추가
사용 하 여 Windows 용 MFC 응용 프로그램을 빌드할 때 일반적으로 [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md), Microsoft Foundation의 핵심 기능을 포함 하는 기본 파일 (리소스 스크립트 (.rc) 파일 포함) 집합을 생성 하는 마법사 클래스 (MFC)입니다. 그러나 MFC를 기반으로 하지 않는 Windows 응용 프로그램용 .rc 파일을 편집하는 경우에는 MFC 프레임워크와 관련된 다음 기능을 사용할 수 없습니다.  
  
-   MFC 코드 마법사 (이전의 "[MFC ClassWizard](http://msdn.microsoft.com/en-us/98dc2434-ba93-4e0b-b084-1a4bc26cdf1e)")  
  
-   메뉴 프롬프트 문자열  
  
-   콤보 상자 컨트롤에 대한 내용 나열  
  
-   ActiveX 컨트롤 호스팅  
  
 그러나 MFC 지원이 없는 기존 .rc 파일에 해당 지원을 추가할 수 있습니다.  
  
### <a name="to-add-mfc-support-to-rc-files"></a>.rc 파일에 MFC 지원을 추가하려면  
  
1.  리소스 스크립트 파일을 엽니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  [리소스 뷰](../windows/resource-view-window.md), 리소스 폴더 (예: MFC.rc)를 강조 표시 합니다.  
  
3.  에 [속성 창](/visualstudio/ide/reference/properties-window)로 설정 된 **MFC Mode** 속성을 **True**합니다.  
  
    > [!NOTE]
    >  이 플래그를 설정하는 것 외에도 .rc 파일은 MFC 프로젝트의 일부여야 합니다. 예를 들어 설정 **MFC Mode** 를 **True** .rc 파일에서 Win32 프로젝트를 제공 하지 않습니다 MFC 기능입니다.  
  

  
 **요구 사항**  
  
 MFC  
  
## <a name="see-also"></a>참고 항목  
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [리소스 편집기](../windows/resource-editors.md)
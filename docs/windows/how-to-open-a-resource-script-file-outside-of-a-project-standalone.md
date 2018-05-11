---
title: '방법: 리소스 스크립트 파일 (독립 실행형) 프로젝트 외부에서 열기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resource
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- rc files, viewing resources
- .rc files, viewing resources
- resource script files, viewing resources
ms.assetid: bc350c60-178d-4c5d-9a7e-6576b0c936e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87dd0cb1e54b6e74c9c4f4fd7d9baff6461ad470
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-open-a-resource-script-file-outside-of-a-project-standalone"></a>방법: 프로젝트 외부에서 리소스 스크립트 파일 열기(독립 실행형)
프로젝트를 열지 않고도 .rc 파일에서 리소스를 볼 수 있습니다. .Rc 파일에서 열리지 않고 문서 창에 열립니다는 [리소스 뷰](../windows/resource-view-window.md) 창 (즉, 프로젝트 내에서 파일이 열릴 때와).  
  
> [!NOTE]
>  일부 명령은 파일이 프로젝트 외부에서 독립 실행형으로 열릴 때만 사용할 수 있으므로 이는 중요한 차이점입니다. 예를 들어 저장할 수 있습니다만 파일을 다른 형식에서 또는 다른 파일 이름으로 해당 파일이 프로젝트 외부에서 열릴 때 (의 **다른 이름으로 저장** 명령을 사용할 수 없는 프로젝트 내부 파일을 열 때).  
  
### <a name="to-open-an-rc-file-outside-a-project"></a>프로젝트 외부에서 .rc 파일을 열려면  
  
1.  **파일** 메뉴 선택 **열려**, 클릭 **파일**합니다.  
  
2.  에 **열려 있는 파일** 대화 상자에서 보고 하 고 파일을 강조 표시를 클릭 하려는 리소스 스크립트 파일을 이동 **열려**합니다.  
  
    > [!NOTE]
    >  프로젝트를 먼저 열면 (**파일**, **열고**, **프로젝트**), 일부 명령을 사용할 수 있습니다. 파일을 "독립 실행형"으로 여는 것은 프로젝트를 먼저 로드하지 않고 파일을 여는 것입니다.  
  
 열고 텍스트 형식에서 리소스 파일을 볼 참조 [리소스 스크립트 (.rc) 파일](../windows/how-to-open-a-resource-script-file-in-text-format.md)합니다.  
  
#### <a name="to-open-multiple-rc-files-outside-a-project"></a>프로젝트 외부에서 여러 .rc 파일을 열려면  
  
1.  두 리소스 파일을 모두 독립 실행형으로 엽니다. 예를 들어 Source1.rc 및 Source2.rc를 엽니다.  
  
    1.  **파일** 메뉴 선택 **열려**, 클릭 **파일**합니다.  
  
    2.  에 **파일 열기** 대화 상자에서 첫 번째 리소스 스크립트 파일 (source1.rc) 파일을 강조 표시 하 고 클릭 하려는 이동 **열고**합니다.  
  
    3.  이전 단계를 반복해서 두 번째 .rc 파일(Source2.rc)을 엽니다.  
  
         .rc 파일이 이제 개별 문서 창으로 열려 있습니다.  
  
2.  두 .rc 파일이 모두 열리면 두 파일을 동시에 볼 수 있도록 창을 바둑판식으로 배열합니다.  
  
    -   **창** 메뉴 선택 **새 가로 탭 그룹** 또는 **새 세로 탭 그룹**합니다.  
  
         \- 또는 -  
  
    -   .Rc 파일 중 하나를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 가로 탭 그룹** 또는 **새 세로 탭 그룹** 바로 가기 메뉴에서.  
  
> [!NOTE]
>  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  

  
### <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [리소스 편집기](../windows/resource-editors.md)
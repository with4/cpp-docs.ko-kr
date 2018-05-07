---
title: 'TN023: 표준 MFC 리소스 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.resources
dev_langs:
- C++
helpviewer_keywords:
- resources [MFC]
- TN023
- standard resources
ms.assetid: 60af8415-c576-4c2f-a711-ca5da0b9a1f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61d6520aef1ec04c6419fb1c9c901475c9c109f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="tn023-standard-mfc-resources"></a>TN023: 표준 MFC 리소스
이 메모와 함께 제공 되 고 MFC 라이브러리에 필요한 표준 리소스를 설명 합니다.  
  
## <a name="standard-resources"></a>표준 리소스  
 MFC에서는 두 가지 범주의 응용 프로그램에서 사용할 수 있는 미리 정의 된 리소스를 제공: 클립 아트 리소스와 표준 프레임 워크 리소스입니다.  
  
 클립 아트 리소스가 프레임 워크에 의존 하지 않지만 응용 프로그램의 사용자 인터페이스에 추가할 수 있는 추가 리소스입니다. MFC 일반 샘플에 포함 된 다음 클립 아트 리소스 [클립 아트](../visual-cpp-samples.md):  
  
-   Common.rc: 있는 단일 파일로 리소스 포함:  
  
    -   큰 컬렉션 다양 한 비즈니스 및 데이터 처리 작업을 나타내는 아이콘입니다.  
  
    -   몇 가지 일반적인 커서 (Afxres.rc 참조)입니다.  
  
    -   여러 도구 모음 단추를 포함 하는 도구 모음 비트맵입니다.  
  
    -   Commdlg.dll에서 사용 되는 비트맵 및 아이콘 리소스.  
  
-   Indicate.rc: 상태 표시줄 키 상태 지표 "CAP" Caps Lock 키에 대 한 예:에 대 한 문자열 리소스를 포함합니다.  
  
-   Prompts.rc:에 대 한 "새 문서 만들기"와 같은 미리 정의 된 각 명령에 대 한 메뉴 프롬프트 문자열 리소스를 포함 하 `ID_FILE_NEW`합니다.  
  
-   Commdlg.rc: Visual c + + 호환.rc 파일 표준 COMMDLG 대화 상자 템플릿을 포함 합니다.  
  
 표준 프레임 워크 리소스가 내부 구현에 대 한 프레임 워크에 따라 달라 집니다 AFX 정의 Id 사용 하 여 리소스입니다. 거의 AFX 정의 된 이러한 리소스를 변경 해야 합니다. 이렇게 하면이 항목의 뒷부분에 설명 된 절차를 따라야 합니다.  
  
 MFC\INCLUDE 디렉터리에 다음과 같은 프레임 워크 리소스가 포함 됩니다.  
  
-   Afxres.rc: 공용 리소스는 프레임 워크에서 사용 합니다.  
  
-   Afxprint.rc: 특정 리소스를 인쇄 합니다.  
  
-   OLE 클라이언트 응용 프로그램에 특정 Afxolecl.rc: 리소스입니다.  
  
-   전체 OLE 서버 응용 프로그램에 특정 Afxolev.rc: 리소스입니다.  
  
## <a name="using-clip-art-resources"></a>클립 아트 리소스를 사용 하 여  
  
#### <a name="to-use-a-clip-art-binary-resource"></a>클립 아트 이진 리소스를 사용 하려면  
  
1.  Visual c + +에서 응용 프로그램의 리소스 파일을 엽니다.  
  
2.  Common.rc를 엽니다. 이 파일에는 이진 클립 아트 리소스를 모두 포함 되어 있습니다. Common.rc 파일은 컴파일됩니다 때문에 다소 시간이 걸릴 수 있습니다.  
  
3.  Ctrl 키를 누른 채 Common.rc에서 응용 프로그램의 리소스 파일을 사용 하려면 리소스를 끕니다.  
  
 다른 클립 아트 리소스를 사용 하려면 동일한 단계를 수행 합니다. 유일한 차이점은 Common.rc 대신 적절 한.rc 파일이 열립니다.  
  
> [!NOTE]
>  실수로 Common.rc에서 리소스를 영구적으로 이동 하지 않도록 주의 하십시오. 리소스를 끌어 동안 CTRL 키를 누른 경우 복사본을 만들게 됩니다. 끌면 동안 CTRL 포함 되지 않은 리소스 이동 됩니다. 위해서 수 실수로 했다고 변경 Common.rc 파일로 Common.rc의 변경 사항을 저장할 것인지 묻는 메시지가 나타나면 "아니요"를 클릭 합니다.  
  
> [!NOTE]
>  .Rc 리소스 파일에는 특별 한 있습니다 `TEXTINCLUDE` 에 실수로 위에 표준.rc 파일에 저장 하면 방해 하는 리소스입니다.  
  
### <a name="customizing-standard-framework-resources"></a>표준 프레임 워크 리소스를 사용자 지정  
 표준 프레임 워크 리소스를 사용 하 여 응용 프로그램에 포함 된 일반적으로 # 응용 프로그램의 리소스 파일에 명령을 include 합니다. 응용 프로그램 마법사는 리소스 파일을 생성 합니다. 이 파일에는 선택한 응용 프로그램 마법사 옵션에 따라 적절 한 표준 프레임 워크 리소스를 포함 합니다. 검토 지정, 추가 또는 제거 컴파일 타임 지시문을 변경 하 여 어떤 리소스가 포함 됩니다. 이 작업을 수행 하려면 엽니다는 **리소스** 메뉴와 선택 **Set Includes**합니다. "컴파일 타임 지시문" 참조 항목을 편집 합니다. 예를 들어:  
  
```  
#include "afxres.rc"  
#include "afxprint.rc"  
```  
  
 표준 프레임 워크 리소스를 사용자 지정의 가장 일반적인 경우는 추가 하거나 추가 제거에 인쇄에 대 한 OLE 클라이언트 및 OLE 서버 지원.  
  
 일부 드문 경우 특정 응용 프로그램에 대 한 표준 프레임 워크 리소스의 콘텐츠를 사용자 지정할 수 있습니다 뿐 아니라 추가 및 전체 파일을 제거 합니다. 다음 단계 포함 되는 리소스를 제한할 수는 방법을 보여 줍니다.  
  
##### <a name="to-customize-the-contents-of-a-standard-resource-file"></a>표준 리소스 파일의 내용을 사용자 지정 하려면  
  
1.  Visual c + +에서 리소스 파일을 엽니다.  
  
2.  Resource Set Includes 명령을 사용 하 여 제거 된 `#include` 사용자 지정 하려면 표준.rc 파일에 대 한 합니다. 예를 들어 인쇄 미리 보기 도구 모음을 사용자 지정 하려면 제거의 `#include "afxprint.rc"` 선입니다.  
  
3.  MFC\INCLUDE에서 적절 한 표준 리소스 파일을 엽니다. 이 항목의 앞부분에 나오는 예제에서는 다음 적절 한 파일은 MFC\Include\Aafxprint.rc  
  
4.  응용 프로그램 리소스 파일을 표준.rc 파일에서 모든 리소스를 복사 합니다.  
  
5.  응용 프로그램 리소스 파일에 표준 리소스의 복사본을 수정 합니다.  
  
> [!NOTE]
>  표준.rc 파일에 직접 리소스를 수정 하지 마십시오. 이렇게 하면 현재 작업 중인 한 뿐 아니라, 모든 응용 프로그램에서 사용할 수 있는 리소스 수정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)


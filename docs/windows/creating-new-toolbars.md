---
title: "새 도구 모음 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.toolbar
dev_langs: C++
helpviewer_keywords:
- toolbars [C++], creating
- Toolbar editor, creating new toolbars
- Insert Resource
ms.assetid: 1b28264b-0718-4df8-9f65-979805d2efef
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4315d101f194b9c0ff1a66b9e7cf81dc778cf372
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-new-toolbars"></a>새 도구 모음 만들기
### <a name="to-create-a-new-toolbar"></a>새 도구 모음을 만들려면  
  
1.  **리소스** 확인.rc 파일을 마우스 오른쪽 단추로 클릭 한 후 선택 **리소스 추가** 바로 가기 메뉴에서. (단추로 단순히 기존 도구 모음.rc 파일에 있는 경우는 **도구 모음** 폴더와 선택 **도구 모음 삽입** 바로 가기 메뉴에서.)  
  
     **참고** 프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  에 **리소스 추가** 대화 상자에서 **도구 모음** 에 **리소스 종류** 목록을 클릭 합니다 **새로**합니다.  
  
     더하기 기호 (+) 옆에 표시 하는 경우는 **도구 모음** 리소스 종류 의미 모음 템플릿을 사용할 수 있습니다. 템플릿의 목록을 확장, 서식 파일을 선택 하 고 클릭를 더하기 기호를 클릭 **새로**합니다.  
  
     \- 또는 -  
  
3.  [도구 모음에 기존 비트맵 변환](../windows/converting-bitmaps-to-toolbars.md)합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
 요구 사항  
  
 MFC 또는 ATL  
  
## <a name="see-also"></a>참고 항목  
 [도구 모음 편집기](../windows/toolbar-editor.md)


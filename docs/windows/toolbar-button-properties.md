---
title: "도구 모음 단추 속성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- size, toolbar buttons
- toolbar buttons (in Toolbar editor), setting properties
- Toolbar editor, toolbar button properties
- status bars, active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5e179cd400b0b8bcc621a7c69a4814eab098fbaa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="toolbar-button-properties"></a>도구 모음 단추 속성
도구 모음 단추의 속성은 같습니다.  
  
|속성|설명|  
|--------------|-----------------|  
|**ID**|단추에 대 한 ID를 정의합니다. 드롭 다운 목록에서는 일반적인 **ID** 이름입니다.|  
|**너비**|단추의 너비를 설정합니다. 16 픽셀 것이 좋습니다.|  
|**높이**|단추의 높이 설정합니다. 참고 한 단추의 높이 도구 모음에 있는 모든 단추의 높이 변경 합니다. 15 픽셀 것이 좋습니다.|  
|**프롬프트**|상태 표시줄에 표시 되는 메시지를 정의 합니다. 도구 모음 단추를 도구 설명 추가 \n과 이름을 추가 합니다. 자세한 내용은 참조 [한 도구 설명 만들기](../windows/creating-a-tool-tip-for-a-toolbar-button.md)합니다.|  
  
 **너비** 및 **높이** 모든 단추에 적용 합니다. 도구 모음을 만드는 데 사용 되는 비트맵은 2048의 최대 너비입니다. 따라서 네 개의 단추를 하나만 사용할 수 있습니다를 512 단추 너비를 설정 및 513에 너비를 설정 하면 세 개의 단추가 하나만 사용할 수 있습니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](/dotnet/standard/globalization-localization/index)합니다.  
  
## <a name="requirements"></a>요구 사항  
 MFC 또는 ATL  
  
## <a name="see-also"></a>참고 항목  
 [도구 모음 단추의 속성 변경](../windows/changing-the-properties-of-a-toolbar-button.md)   
 [도구 모음 편집기](../windows/toolbar-editor.md)


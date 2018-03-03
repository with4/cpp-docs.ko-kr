---
title: "방법: 리소스에서 기호 검색 | Microsoft Docs"
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
- symbols, finding
- resources [Visual Studio], searching for symbols
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 154c7a7284272ceef7a3e2d82fcd90d05069b7fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-search-for-symbols-in-resources"></a>방법: 리소스에서 기호 검색
### <a name="to-find-symbols-in-resources"></a>리소스에서 기호를 찾으려면  
  
1.  **편집** 메뉴 선택 **기호 찾기**합니다.  
  
2.  에 [기호 찾기 대화 상자](http://msdn.microsoft.com/en-us/63e93d9c-784f-418d-a76a-723da5ff5d96)에 **찾을 내용** 상자, 드롭 다운 목록에서 이전 검색 문자열을 선택 하거나 (예: ID_ACCEL1) 찾으려는 액셀러레이터 키를 입력 합니다.  
  
    > [!TIP]
    >  사용 하도록 [정규식](/visualstudio/ide/using-regular-expressions-in-visual-studio) 의 검색을 사용 해야 합니다는 [파일에서에서 찾기 명령](/visualstudio/ide/reference/find-command) 에서 **편집** 대신 메뉴는 **기호 찾기**명령입니다. 정규식을 사용 하도록 설정 하려면 있어야는 **사용: 정규식** 확인란을 선택는 [찾기 대화 상자](http://msdn.microsoft.com/en-us/dad03582-4931-4893-83ba-84b37f5b1600)합니다. 오른쪽의 오른쪽 화살표 단추를 클릭 한 다음는 **찾을 내용** 상자 정규 검색 식의 목록을 표시 합니다. 이 목록에서 식을 선택 하면 검색 텍스트로 대체 됩니다는 **찾을 내용** 상자입니다.  
  
3.  중 하나를 선택는 **찾을** 옵션입니다.  
  
4.  클릭 **다음 찾기**합니다.  
  
    > [!NOTE]
    >  문자열, 액셀러레이터 또는 이진 리소스에서 기호를 검색할 수 없습니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)를 선택합니다.  
  
 **요구 사항**  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [기호: 리소스 식별자](../windows/symbols-resource-identifiers.md)   
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [리소스 편집기](../windows/resource-editors.md)
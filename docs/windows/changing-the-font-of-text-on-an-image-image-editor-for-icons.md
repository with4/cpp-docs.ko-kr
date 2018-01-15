---
title: "이미지 (아이콘에 대 한 이미지 편집기)의 텍스트 글꼴 변경 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: fonts, changing on an image
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 07dc7d7fd74ad9d4b0229ffef7cf4e96a4ea44b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="changing-the-font-of-text-on-an-image-image-editor-for-icons"></a>이미지의 텍스트 글꼴 변경(아이콘에 대한 이미지 편집기)
다음 절차에는 하는 방법의 예입니다.  
  
-   텍스트를 Windows 응용 프로그램에서 아이콘 추가  
  
-   텍스트의 글꼴을 조작  
  
### <a name="to-change-the-font-of-text-on-an-image"></a>이미지의 텍스트 글꼴을 변경 하려면  
  
1.  C + + Windows Forms 응용 프로그램을 만듭니다. 자세한 내용은 참조 [Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)합니다. [Windows Forms 응용 프로그램 템플릿](http://msdn.microsoft.com/en-us/1babdebf-ab3f-4a64-a608-98499a5b9cea) app.ico 프로젝트에 기본적으로 명명 된 파일을 추가 합니다.  
  
2.  솔루션 탐색기에서 app.ico 파일을 두 번 클릭 합니다. [이미지 편집기](../windows/image-editor-for-icons.md) 열립니다.  
  
3.  **이미지** 메뉴 선택 **도구** 선택한 후 **텍스트 도구**합니다. [텍스트 도구 대화 상자](../windows/text-tool-dialog-box-image-editor-for-icons.md) 표시 됩니다.  
  
4.  텍스트 도구 대화 상자에 입력 `C++` 빈 텍스트 영역에 있습니다. 이 텍스트는 app.ico 이미지 편집기의 왼쪽된 위 모퉁이에 있는 크기 조정 가능한 상자에 표시 됩니다.  
  
5.  이미지 편집기에서 텍스트의 가독성을 높이기 위해 app.ico의 가운데에 크기 조정 가능한 상자를 끕니다.  
  
6.  텍스트 도구 대화 상자에서 클릭 된 **글꼴** 단추입니다. [텍스트 도구 글꼴 대화 상자](../windows/text-tool-font-dialog-box-image-editor-for-icons.md) 표시 됩니다.  
  
7.  텍스트 도구 글꼴 대화 상자에서 선택 **Times New Roman** 목록에 나열 된 사용 가능한 글꼴에서 **글꼴** 목록 상자입니다.  
  
8.  선택 **b o l d** 에 나열 된 사용 가능한 글꼴 스타일 목록에서는 **글꼴 스타일** 목록 상자입니다.  
  
9. 선택 **10** 포인트에 나열 된 크기의 사용 가능한 목록에서는 **크기** 목록 상자입니다.  
  
10. 클릭는 **확인** 단추입니다. 텍스트 도구 글꼴 대화 상자를 닫히고 새 글꼴 설정을 텍스트에 적용 됩니다.  
  
11. 클릭는 **닫기** 텍스트 도구 대화 상자에서 단추입니다. 텍스트 주위의 크기 조정 가능한 상자에는 이미지 편집기에서 사라집니다.  
  
## <a name="see-also"></a>참고 항목  
 [그래픽 리소스 편집](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [도구 모음](../windows/toolbar-image-editor-for-icons.md)


---
title: "오류 트래핑 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], 오류 트래핑"
  - "오류 트래핑[C++]"
ms.assetid: c509b089-a542-44be-8f22-dc5832967a48
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 오류 트래핑
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터 바인딩에서 오류 트래핑은 두 소스인 오류 이벤트나 오류 개체로부터 발생합니다.  
  
##  <a name="vcreferrortrappingviaerrorevents"></a> 오류 이벤트를 통해 오류 트래핑  
 ADO 데이터 컨트롤과 RDO RemoteData 컨트롤의 데이터 컨트롤에는 모두 오류 이벤트가 있습니다.  일반적으로 사용자가 오류 이벤트 처리기를 설정합니다.  이벤트 처리기에는 다음과 같은 시그니처가 있어야 합니다.  
  
```  
void CMyDlg::OnErrorAdodc1(long ErrorNumber,  
                           BSTR* FAR Description,  
                           long Scode,  
                           LPCTSTR Source,  
                           LPCTSTR HelpFile,  
                           long HelpContext,  
                           BOOL FAR* fCancelDisplay)  
```  
  
 일반적으로 Description 필드는 채워져 있지만 ErrorNumber 필드와 Scode 필드는 COM 오류일 경우에만 채워집니다.  표준 이벤트 처리기는 메시지 상자에 Description 필드를 표시합니다.  예를 들면 다음과 같습니다.  
  
```  
{  
   USES_CONVERSION;     
// note: have to include the ATL file ATLConv.h to use the ATL conversion macros  
   ::AfxMessageBox(OLE2T(*Description), MB_OK);  
}  
```  
  
 그러나 ADO 데이터 컨트롤과 RDO RemoteData 컨트롤은 오류 이벤트를 트래핑하도록 설정되어 있으므로 코드 작업이 필요하지 않습니다.  
  
##  <a name="vcreferrortrappingviaerrorobjects"></a> 오류 개체를 통해 오류 트래핑  
 ADO와 RDO에는 모두 오류 개체가 있습니다.  RDO RemoteData 컨트롤은 [래퍼 클래스](../../data/ado-rdo/wrapper-classes.md)를 생성할 때 오류 개체에 대한 래퍼를 생성하지만 ADO 데이터 컨트롤은 오류 개체에 대한 래퍼를 생성하지 않습니다.  
  
 ADO 데이터 컨트롤은 ADO 오류 메시지를 자동으로 표시합니다.  
  
## 참고 항목  
 [Visual C\+\+에서 ActiveX 컨트롤을 사용하여 데이터 바인딩](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)
---
title: "TN022: 표준 명령 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.commands"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "명령, 표준"
  - "ID_APP_ABOUT 명령"
  - "ID_APP_EXIT 명령"
  - "ID_CONTEXT_HELP 명령"
  - "ID_DEFAULT_HELP 명령"
  - "ID_EDIT_CLEAR 명령"
  - "ID_EDIT_CLEAR_ALL 명령"
  - "ID_EDIT_COPY 명령"
  - "ID_EDIT_CUT 명령"
  - "ID_EDIT_FIND 명령"
  - "ID_EDIT_PASTE 명령"
  - "ID_EDIT_PASTE_LINK 명령"
  - "ID_EDIT_PASTE_SPECIAL 명령"
  - "ID_EDIT_REDO 명령"
  - "ID_EDIT_REPEAT 명령"
  - "ID_EDIT_REPLACE 명령"
  - "ID_EDIT_SELECT_ALL 명령"
  - "ID_EDIT_UNDO 명령"
  - "ID_FILE_CLOSE 명령"
  - "ID_FILE_NEW 명령"
  - "ID_FILE_OPEN 명령"
  - "ID_FILE_PAGE_SETUP 명령"
  - "ID_FILE_PRINT 명령"
  - "ID_FILE_PRINT_PREVIEW 명령"
  - "ID_FILE_PRINT_SETUP 명령"
  - "ID_FILE_SAVE 명령"
  - "ID_FILE_SAVE_AS 명령"
  - "ID_FILE_SAVE_COPY_AS 명령"
  - "ID_FILE_UPDATE 명령"
  - "ID_HELP 명령"
  - "ID_HELP_INDEX 명령"
  - "ID_HELP_USING 명령"
  - "ID_INDICATOR_CAPS 명령"
  - "ID_INDICATOR_EXT 명령"
  - "ID_INDICATOR_KANA 명령"
  - "ID_INDICATOR_NUM 명령"
  - "ID_INDICATOR_OVR 명령"
  - "ID_INDICATOR_REC 명령"
  - "ID_INDICATOR_SCRL 명령"
  - "ID_NEXT_PANE 명령"
  - "ID_OLE_EDIT_LINKS 명령"
  - "ID_OLE_INSERT_NEW 명령"
  - "ID_OLE_VERB_FIRST 명령"
  - "ID_PREV_PANE 명령"
  - "ID_VIEW_STATUS_BAR 명령"
  - "ID_VIEW_TOOLBAR 명령"
  - "ID_WINDOW_ARRANGE 명령"
  - "ID_WINDOW_CASCADE 명령"
  - "ID_WINDOW_NEW 명령"
  - "ID_WINDOW_SPLIT 명령"
  - "ID_WINDOW_TILE_HORZ 명령"
  - "ID_WINDOW_TILE_VERT 명령"
  - "표준 명령"
  - "TN022"
ms.assetid: a7883b46-23f7-4870-ac3a-804aed9258b5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# TN022: 표준 명령 구현
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다.  따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다.  최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 This note describes the standard command implementations provided by MFC 2.0.  Read [Technical Note 21](../mfc/tn021-command-and-message-routing.md) first because it describes the mechanisms used to implement many of the standard commands.  
  
 This description assumes knowledge of the MFC architectures, APIs, and common programming practice.  Documented as well as undocumented "implementation only" APIs are described.  This is not a place to start learning about the features of or how to program in MFC.  Refer to Visual C\+\+ for more general information and for details of documented APIs.  
  
## The Problem  
 MFC defines many standard command IDs in the header file AFXRES.H.  Framework support for these commands varies.  Understanding where and how the framework classes handle these commands will not only show you how the framework works internally but will provide useful information on how to customize the standard implementations and teach you a few techniques for implementing your own command handlers.  
  
## Contents of This Technical Note  
 Each command ID is described in two sections:  
  
-   The title: the symbolic name of the command ID \(for example, **ID\_FILE\_SAVE**\) followed by the purpose of the command \(for example, "saves the current document"\) separated by a colon.  
  
-   One or more paragraphs describing which classes implement the command, and what the default implementation does  
  
 Most default command implementations are prewired in the framework's base class message map.  There are some command implementations that require explicit wiring in your derived class.  These are described under "Note".  If you chose the right options in AppWizard, these default handlers will be connected for you in the generated skeleton application.  
  
## 명명 규칙  
 Standard commands follow a simple naming convention that we recommend you use if possible.  Most standard commands are located in standard places in an application's menu bar.  The symbolic name of the command starts with "ID\_" followed by the standard pop\-up menu name, followed by the menu item name.  The symbolic name is in upper case with underscore word\-breaks.  For commands that do not have standard menu item names, a logical command name is defined starting with "ID\_" \(for example, **ID\_NEXT\_PANE**\).  
  
 We use the prefix "ID\_" to indicate commands that are designed to be bound to menu items, toolbar buttons, or other command user\-interface objects.  Command handlers handling "ID\_" commands should use the `ON_COMMAND` and `ON_UPDATE_COMMAND_UI` mechanisms of the MFC command architecture.  
  
 We recommend you use the standard "IDM\_" prefix for menu items which do not follow the command architecture and need menu\-specific code to enable and disable them.  Of course the number of menu specific commands should be small since following the MFC command architecture not only makes command handlers more powerful \(since they will work with toolbars\) but makes the command handler code reusable.  
  
## ID Ranges  
 Please refer to [Technical Note 20](../mfc/tn020-id-naming-and-numbering-conventions.md) for more details on the use of ID ranges in MFC.  
  
 MFC standard commands fall in the range 0xE000 to 0xEFFF.  Please do not rely on the specific values of these IDs since they are subject to change in future versions of the library.  
  
 Your application should define its commands in the range 0x8000 to 0xDFFF.  
  
## Standard Command IDs  
 For each command ID, there is a standard message line prompt string that can be found in the file PROMPTS.RC.  The string ID for that menu prompt must be the same as for the command ID.  
  
-   ID\_FILE\_NEW   Creates a new\/empty document.  
  
    > [!NOTE]
    >  You must connect this to your `CWinApp`\-derived class's message map to enable this functionality.  
  
     `CWinApp::OnFileNew` implements this command differently depending on the number of document templates in the application.  If there is only one `CDocTemplate`, `CWinApp::OnFileNew` will create a new document of that type, as well as the proper frame and view class.  
  
     If there is more than one `CDocTemplate`, `CWinApp::OnFileNew` will prompt the user with a dialog \(**AFX\_IDD\_NEWTYPEDLG**\) letting them select which document type to use.  The selected `CDocTemplate` is used to create the document.  
  
     One common customization of `ID_FILE_NEW` is to provide a different and more graphical choice of document types.  In this case you can implement your own **CMyApp::OnFileNew** and place it in your message map instead of `CWinApp::OnFileNew`.  There is no need to call the base class implementation.  
  
     Another common customization of `ID_FILE_NEW` is to provide a separate command for creating a document of each type.  In this case you should define new command IDs, for example ID\_FILE\_NEW\_CHART and ID\_FILE\_NEW\_SHEET.  
  
-   ID\_FILE\_OPEN   Opens an existing document.  
  
    > [!NOTE]
    >  You must connect this to your `CWinApp`\-derived class's message map to enable this functionality.  
  
     `CWinApp::OnFileOpen` has a very simple implementation of calling **CWinApp::DoPromptFileName** followed by `CWinApp::OpenDocumentFile` with the file or path name of the file to open.  The `CWinApp` implementation routine **DoPromptFileName** brings up the standard FileOpen dialog and fills it with the file extensions obtained from the current document templates.  
  
     One common customization of `ID_FILE_OPEN` is to customize the FileOpen dialog or add additional file filters.  The recommended way to customize this is to replace the default implementation with your own FileOpen dialog, and call `CWinApp::OpenDocumentFile` with the document's file or path name.  There is no need to call the base class.  
  
-   ID\_FILE\_CLOSE   Closes the currently open document.  
  
     **CDocument::OnFileClose** calls `CDocument::SaveModified` to prompt the user to save the document if it has been modified and then calls `OnCloseDocument`.  All the closing logic, including destroying the document, is done in the `OnCloseDocument` routine.  
  
    > [!NOTE]
    >  **ID\_FILE\_CLOSE** acts differently from a `WM_CLOSE` message or an **SC\_CLOSE** system command sent to the documents frame window.  Closing a window will close the document only if that is the last frame window showing the document.  Closing the document with **ID\_FILE\_CLOSE** will not only close the document but will close down all frame windows showing the document.  
  
-   ID\_FILE\_SAVE   Saves the current document.  
  
     The implementation uses a helper routine **CDocument::DoSave** which is used for both **OnFileSave** and **OnFileSaveAs**.  If you save a document that has not been saved before \(that is, it does not have a path name, as in the case of FileNew\) or that was read from a read\-only document, the **OnFileSave** logic will act like the **ID\_FILE\_SAVE\_AS** command and ask the user to provide a new file name.  The actual process of opening the file and doing the saving is done through the virtual function `OnSaveDocument`.  
  
     There are two common reasons to customize **ID\_FILE\_SAVE**.  For documents that do not save, simply remove the **ID\_FILE\_SAVE** menu items and toolbar buttons from your user interface.  Also make sure that you never dirty your document \(that is, never call `CDocument::SetModifiedFlag`\) and the framework will never cause the document to be saved.  For documents that save to someplace other than a disk file, define a new command for that operation.  
  
     In the case of a `COleServerDoc`, **ID\_FILE\_SAVE** is used both for file save \(for normal documents\) and file update \(for embedded documents\).  
  
     If your document data is stored in individual disk files, but you don't want to use the default **CDocument** serialize implementation, you should override `CDocument::OnSaveDocument` instead of **OnFileSave**.  
  
-   ID\_FILE\_SAVE\_AS   Saves the current document under a different file name.  
  
     The **CDocument::OnFileSaveAs** implementation uses the same **CDocument::DoSave** helper routine as **OnFileSave**.  The **OnFileSaveAs** command is handled just as **ID\_FILE\_SAVE** if the documents had no file name before the save.  **COleServerDoc::OnFileSaveAs** implements the logic to save a normal document data file or to save a server document representing an OLE object embedded in some other application as a separate file.  
  
     If you customize the logic of **ID\_FILE\_SAVE**, you will probably want to customize **ID\_FILE\_SAVE\_AS** in a similar fashion or the operation of "Save As" may not apply to your document.  You can remove the menu item from your menu bar if it is not needed.  
  
-   ID\_FILE\_SAVE\_COPY\_AS   Saves a copy current document under a new name.  
  
     The **COleServerDoc::OnFileSaveCopyAs** implementation is very similar to **CDocument::OnFileSaveAs**, except that the document object is not "attached" to the underlying file after the save.  That is, if the in\-memory document was "modified" before the save, it is still "modified".  In addition, this command has no effect on the path name or title stored in the document.  
  
-   ID\_FILE\_UPDATE   Notifies the container to save an embedded document.  
  
     The `COleServerDoc::OnUpdateDocument` implementation simply notifiies the container that the embedding should be saved.  The container then calls the appropriate OLE APIs in order to save the embedded object.  
  
-   ID\_FILE\_PAGE\_SETUP   Invokes an application\-specific page setup\/layout dialog.  
  
     Currently there is no standard for this dialog, and the framework has no default implementation of this command.  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
-   ID\_FILE\_PRINT\_SETUP   Invoke the standard Print Setup dialog.  
  
    > [!NOTE]
    >  You must connect this to your `CWinApp`\-derived class's message map to enable this functionality.  
  
     This command invokes the standard print setup dialog that allows the user to customize the printer and print settings for at least this document or at most all the documents in this application.  You must use the Control Panel to change the default printer settings for the entire system.  
  
     `CWinApp::OnFilePrintSetup` has a very simple implementation creating a `CPrintDialog` object and calling the **CWinApp::DoPrintDialog** implementation function.  This sets the application default printer setup.  
  
     The common need for customizing this command is to allow for per\-document printer settings, which should be stored with the document when saved.  To do this you should add a message\-map handler in your **CDocument** class that creates a `CPrintDialog` object, initializes it with the appropriate printer attributes \(usually **hDevMode** and **hDevNames**\), call the **CPrintDialog::DoModal,** and save the changed printer settings.  For a robust implementation, you should look at the implementation of **CWinApp::DoPrintDialog** for detecting errors and **CWinApp::UpdatePrinterSelection** for dealing with sensible defaults and tracking system\-wide printer changes.  
  
-   ID\_FILE\_PRINT   Standard printing of the current document  
  
    > [!NOTE]
    >  You must connect this to your `CView`\-derived class's message map to enable this functionality.  
  
     This command prints the current document, or more correctly, starts the printing process, which involves invoking the standard print dialog and running the print engine.  
  
     **CView::OnFilePrint** implements this command and the main print loop.  It calls the virtual `CView::OnPreparePrinting` to prompt of the user with the print dialog.  It then prepares the output DC to go to the printer, brings up the printing progress dialog \(**AFX\_IDD\_PRINTDLG**\), and sends the `StartDoc` escape to the printer.  **CView::OnFilePrint** also contains the main page\-oriented print loop.  For each page, it calls the virtual `CView::OnPrepareDC` followed by a `StartPage` escape and calling the virtual `CView::OnPrint` for that page.  When complete, the virtual `CView::OnEndPrinting` is called, and the printing progress dialog is closed.  
  
     The MFC printing architecture is designed to hook in many different ways for printing and print preview.  You will normally find the various `CView` overridable functions adequate for any page\-oriented printing tasks.  Only in the case of an application that uses the printer for non\-page oriented output, should you find the need to replace the **ID\_FILE\_PRINT** implementation.  
  
-   ID\_FILE\_PRINT\_PREVIEW   Enter print\-preview mode for the current document.  
  
    > [!NOTE]
    >  You must connect this to your `CView`\-derived class's message map to enable this functionality.  
  
     **CView::OnFilePrintPreview** starts the print preview mode by calling the documented helper function **CView::DoPrintPreview**.  **CView::DoPrintPreview** is the main engine for the print preview loop, just as **OnFilePrint** is the main engine for the printing loop.  
  
     The print preview operation can be customized in a variety of ways by passing different parameters to **DoPrintPreview**.  Please refer to [Technical Note 30](../mfc/tn030-customizing-printing-and-print-preview.md), which discusses some of the details of print preview and how to customize it.  
  
-   **ID\_FILE\_MRU\_FILE1**...**FILE16** A range of command IDs for the File MRU `list`.  
  
     **CWinApp::OnUpdateRecentFileMenu** is a update command UI handler that is one of the more advanced uses of the `ON_UPDATE_COMMAND_UI` mechanism.  In your menu resource, you need only define a single menu item with ID **ID\_FILE\_MRU\_FILE1**.  That menu item remains initially disabled.  
  
     As the MRU list grows, more menu items are added to the list.  The standard `CWinApp` implementation defaults to the standard limit of the four most recently used files.  You can change the default by calling `CWinApp::LoadStdProfileSettings` with a larger or smaller value.  The MRU list is stored in the application's .INI file.  The list is loaded in your application's `InitInstance` function if you call `LoadStdProfileSettings`, and is saved when your application exits.  The MRU update command UI handler also will convert absolute paths to relative paths for display on the file menu.  
  
     **CWinApp::OnOpenRecentFile** is the `ON_COMMAND` handler that performs the actual command.  It simply gets the file name from the MRU list and calls `CWinApp::OpenDocumentFile`, which does all the work of opening the file and updating the MRU list.  
  
     Customization of this command handler is not recommended.  
  
-   ID\_EDIT\_CLEAR   Clears the current selection  
  
     Currently there is no standard implementation for this command.  You must implement this for each `CView`\-derived class.  
  
     `CEditView` provides an implementation of this command using `CEdit::Clear`.  The command is disabled if there is no current selection.  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
-   ID\_EDIT\_CLEAR\_ALL   Clears the entire document.  
  
     Currently there is no standard implementation for this command.  You must implement this for each `CView`\-derived class.  
  
     If you choose to implement this command, we recommend you use this command ID.  See the MFC Tutorial sample [SCRIBBLE](../top/visual-cpp-samples.md) for an example implementation.  
  
-   ID\_EDIT\_COPY   Copies the current selection to the Clipboard.  
  
     Currently there is no standard implementation for this command.  You must implement this for each `CView`\-derived class.  
  
     `CEditView` provides an implementation of this command, which copies the currently selected text to the Clipboard as CF\_TEXT using `CEdit::Copy`.  The command is disabled if there is no current selection.  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
-   ID\_EDIT\_CUT   Cuts the current selection to the Clipboard.  
  
     Currently there is no standard implementation for this command.  You must implement this for each `CView`\-derived class.  
  
     `CEditView` provides an implementation of this command, which cuts the currently selected text to the Clipboard as CF\_TEXT using `CEdit::Cut`.  The command is disabled if there is no current selection.  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
-   ID\_EDIT\_FIND   Begins the find operation, brings up the modeless find dialog.  
  
     Currently there is no standard implementation for this command.  You must implement this for each `CView`\-derived class.  
  
     `CEditView` provides an implementation of this command, which calls the implementation helper function **OnEditFindReplace** to use and store the previous find\/replace settings in private implementation variables.  The `CFindReplaceDialog` class is used to manage the modeless dialog for prompting the user.  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
-   ID\_EDIT\_PASTE   Inserts the current Clipboard contents.  
  
     Currently there is no standard implementation for this command.  You must implement this for each `CView`\-derived class.  
  
     `CEditView` provides an implementation of this command, which copies the current Clipboard data replacing the selected text using `CEdit::Paste`.  The command is disabled if there is no **CF\_TEXT** in the Clipboard.  
  
     **COleClientDoc** just provides a update command UI handler for this command.  If the Clipboard does not contain an embeddable OLE item\/object, the command will be disabled.  You are responsible for writing the handler for the actual command to do the actual pasting.  If your OLE application can also paste other formats, you should provide your own update command UI handler in your view or document \(that is, somewhere before **COleClientDoc** in the command target routing\).  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
     For replacing the standard OLE implementation, use `COleClientItem::CanPaste`.  
  
-   ID\_EDIT\_PASTE\_LINK   Inserts a link from the current Clipboard contents.  
  
     Currently there is no standard implementation for this command.  You must implement this for each `CView`\-derived class.  
  
     `COleDocument` just provides a update command UI handler for this command.  If the Clipboard does not contain linkable OLE item\/object, the command will be disabled.  You are responsible for writing the handler for the actual command to do the actual pasting.  If your OLE application can also paste other formats, you should provide your own update command UI handler in your view or document \(that is, somewhere before `COleDocument` in the command target routing\).  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
     For replacing the standard OLE implementation, use `COleClientItem::CanPasteLink`.  
  
-   ID\_EDIT\_PASTE\_SPECIAL   Inserts the current Clipboard contents with options.  
  
     Currently there is no standard implementation for this command.  You must implement this for each `CView`\-derived class.  MFC does not provide this dialog.  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
-   ID\_EDIT\_REPEAT   Repeats the last operation.  
  
     Currently there is no standard implementation for this command.  You must implement this for each `CView`\-derived class.  
  
     `CEditView` provides an implementation of this command to repeat the last find operation.  The private implementation variables for the last find are used.  The command is disabled if a find cannot be attempted.  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
-   ID\_EDIT\_REPLACE   Begins the replace operation, brings up the modeless replace dialog.  
  
     Currently there is no standard implementation for this command.  You must implement this for each `CView`\-derived class.  
  
     `CEditView` provides an implementation of this command, which calls the implementation helper function **OnEditFindReplace** to use and store the previous find\/replace settings in private implementation variables.  The `CFindReplaceDialog` class is used to manage the modeless dialog that prompts the user.  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
-   ID\_EDIT\_SELECT\_ALL   Selects the entire document.  
  
     Currently there is no standard implementation for this command.  You must implement this for each `CView`\-derived class.  
  
     `CEditView` provides an implementation of this command, which selects all the text in the document.  The command is disabled if there is no text to select.  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
-   ID\_EDIT\_UNDO   Undoes the last operation.  
  
     Currently there is no standard implementation for this command.  You must implement this for each `CView`\-derived class.  
  
     `CEditView` provides an implementation of this command, using `CEdit::Undo`.  The command is disabled if `CEdit::CanUndo` returns FALSE.  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
-   ID\_EDIT\_REDO   Redoes the last operation.  
  
     Currently there is no standard implementation for this command.  You must implement this for each `CView`\-derived class.  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
-   ID\_WINDOW\_NEW   Opens another window on the active document.  
  
     **CMDIFrameWnd::OnWindowNew** implements this powerful feature by using the document template of the current document to create another frame containing another view of the current document.  
  
     Like most multiple document interface \(MDI\) Window menu commands, the command is disabled if there is no active MDI child window.  
  
     Customization of this command handler is not recommended.  If you wish to provide a command that creates additional views or frame windows, you will probably be better off inventing your own command.  You can clone the code from **CMDIFrameWnd::OnWindowNew** and modify it to the specific frame and view classes of your liking.  
  
-   ID\_WINDOW\_ARRANGE   Arranges icons at the bottom of an MDI window.  
  
     `CMDIFrameWnd` implements this standard MDI command in an implementation helper function **OnMDIWindowCmd**.  This helper maps command IDs to MDI Windows messages and can therefore share a lot of code.  
  
     Like most MDI Window menu commands, the command is disabled if there is no active MDI child window.  
  
     Customization of this command handler is not recommended.  
  
-   ID\_WINDOW\_CASCADE   Cascades windows so they overlap.  
  
     `CMDIFrameWnd` implements this standard MDI command in an implementation helper function **OnMDIWindowCmd**.  This helper maps command IDs to MDI Windows messages and can therefore share a lot of code.  
  
     Like most MDI Window menu commands, the command is disabled if there is no active MDI child window.  
  
     Customization of this command handler is not recommended.  
  
-   ID\_WINDOW\_TILE\_HORZ   Tiles windows horizontally.  
  
     This command is implemented in `CMDIFrameWnd` just like **ID\_WINDOW\_CASCADE**, except a different MDI Windows message is used for the operation.  
  
     You should pick the default tile orientation for your application.  You can do this by changing the ID for the Window "Tile" menu item to either **ID\_WINDOW\_TILE\_HORZ** or **ID\_WINDOW\_TILE\_VERT**.  
  
-   ID\_WINDOW\_TILE\_VERT   Tiles windows vertically.  
  
     This command is implemented in `CMDIFrameWnd` just like **ID\_WINDOW\_CASCADE**, except a different MDI Windows message is used for the operation.  
  
     You should pick the default tile orientation for your application.  You can do this by changing the ID for the Window "Tile" menu item to either **ID\_WINDOW\_TILE\_HORZ** or **ID\_WINDOW\_TILE\_VERT**.  
  
-   ID\_WINDOW\_SPLIT   Keyboard interface to splitter.  
  
     `CView` handles this command for the `CSplitterWnd` implementation.  If the view is part of a splitter window, this command will delegate to the implementation function `CSplitterWnd::DoKeyboardSplit`.  This will place the splitter in a mode that will allow keyboard users to split or unsplit a splitter window.  
  
     This command is disabled if the view is not in a splitter.  
  
     Customization of this command handler is not recommended.  
  
-   ID\_APP\_ABOUT   Invokes the About dialog box.  
  
     There is no standard implementation for an application's About box.  The default AppWizard\-created application will create a custom dialog class for your application and use it as your About box.  AppWizard will also write the trivial command handler which handles this command and invokes the dialog.  
  
     You will almost always implement this command.  
  
-   ID\_APP\_EXIT   Exit the application.  
  
     **CWinApp::OnAppExit** handles this command by sending a `WM_CLOSE` message to the application's main window.  The standard shutting down of the application \(prompting for dirty files and so on\) is handled by the `CFrameWnd` implementation.  
  
     Customization of this command handler is not recommended.  Overriding `CWinApp::SaveAllModified` or the `CFrameWnd` closing logic is recommended.  
  
     If you choose to implement this command, we recommend you use this command ID.  
  
-   ID\_HELP\_INDEX   Lists Help topics from .HLP file.  
  
    > [!NOTE]
    >  You must connect this to your `CWinApp`\-derived class's message map to enable this functionality.  
  
     `CWinApp::OnHelpIndex` handles this command by trivially calling `CWinApp::WinHelp`.  
  
     Customization of this command handler is not recommended.  
  
-   ID\_HELP\_USING   Displays help on how to use Help.  
  
    > [!NOTE]
    >  You must connect this to your `CWinApp`\-derived class's message map to enable this functionality.  
  
     `CWinApp::OnHelpUsing` handles this command by trivially calling `CWinApp::WinHelp`.  
  
     Customization of this command handler is not recommended.  
  
-   ID\_CONTEXT\_HELP   Enters SHIFT\-F1 help mode.  
  
    > [!NOTE]
    >  You must connect this to your `CWinApp`\-derived class's message map to enable this functionality.  
  
     `CWinApp::OnContextHelp` handles this command by setting the help mode cursor, entering a modal loop and waiting for the user to select a window to get help on.  Please refer to [Technical Note 28](../mfc/tn028-context-sensitive-help-support.md) for more details on the MFC Help implementation.  
  
     Customization of this command handler is not recommended.  
  
-   ID\_HELP   Gives help on the current context  
  
    > [!NOTE]
    >  You must connect this to your `CWinApp`\-derived class's message map to enable this functionality.  
  
     `CWinApp::OnHelp` handles this command by getting the right help context for the current application context.  This handles simple F1 help, help on message boxes and so on.  Please refer to [Technical Note 28](../mfc/tn028-context-sensitive-help-support.md) for more details on the MFC help implementation.  
  
     Customization of this command handler is not recommended.  
  
-   ID\_DEFAULT\_HELP   Displays default help for context  
  
    > [!NOTE]
    >  You must connect this to your `CWinApp`\-derived class's message map to enable this functionality.  
  
     This command is usually mapped to `CWinApp::OnHelpIndex`.  
  
     A different command handler can be provided if a distinction between default Help and the Help index is desired.  
  
-   ID\_NEXT\_PANE   Goes to next pane  
  
     `CView` handles this command for the `CSplitterWnd` implementation.  If the view is part of a splitter window, this command will delegate to the implementation function **CSplitterWnd::OnNextPaneCmd**.  This will move the active view to the next pane in the splitter.  
  
     This command is disabled if the view is not in a splitter or there is no next pane to go to.  
  
     Customization of this command handler is not recommended.  
  
-   ID\_PREV\_PANE   Goes to previous pane  
  
     `CView` handles this command for the `CSplitterWnd` implementation.  If the view is part of a splitter window, this command will delegate to the implementation function **CSplitterWnd::OnNextPaneCmd**.  This will move the active view to the previous pane in the splitter.  
  
     This command is disabled if the view is not in a splitter or there is no previous pane to go to.  
  
     Customization of this command handler is not recommended.  
  
-   ID\_OLE\_INSERT\_NEW   Inserts a new OLE object  
  
     Currently there is no standard implementation for this command.  You must implement this for your `CView`\-derived class to insert a new OLE item\/object at the current selection.  
  
     All OLE client applications should implement this command.  AppWizard, with the OLE option, will create a skeleton implementation of **OnInsertObject** in your view class that you will have to complete.  
  
     See the MFC OLE sample [OCLIENT](../top/visual-cpp-samples.md) example for a complete implementation of this command.  
  
-   ID\_OLE\_EDIT\_LINKS   Edits OLE links  
  
     `COleDocument` handles this command by using the MFC\-provided implementation of the standard OLE links dialog.  The implementation of this dialog is accessed through the `COleLinksDialog` class.  If the current document does not contain any links, the command is disabled.  
  
     Customization of this command handler is not recommended.  
  
-   ID\_OLE\_VERB\_FIRST...LAST   An ID range for OLE verbs  
  
     `COleDocument` uses this command ID range for the verbs supported by the currently selected OLE item\/object.  This must be a range since a given OLE item\/object type can support zero or more custom verbs.  In your application's menu, you should have one menu item with the ID of **ID\_OLE\_VERB\_FIRST**.  When the program is run, the menu will be updated with the appropriate menu verb description \(or pop\-up menu with many verbs\).  The management of the OLE menu is handled by `AfxOleSetEditMenu`, done in the update command UI handler for this command.  
  
     There are no explicit command handlers for handling each of the command ID in this range.  **COleDocument::OnCmdMsg** is overridden to trap all command IDs in this range, turn them into zero\-based verb numbers, and launch the server for that verb \(using `COleClientItem::DoVerb`\).  
  
     Customization or other use of this command ID range is not recommended.  
  
-   ID\_VIEW\_TOOLBAR   Toggles the toolbar on and off  
  
     `CFrameWnd` handles this command and the update\-command UI handler to toggle the visible state of the toolbar.  The toolbar must be a child window of the frame with child window ID of `AFX_IDW_TOOLBAR`.  The command handler actually toggles the visibility of the toolbar window.  `CFrameWnd::RecalcLayout` is used to redraw the frame window with the toolbar in its new state.  The update\-command UI handler checks the menu item when the toolbar is visible.  
  
     Customization of this command handler is not recommended.  If you wish to add additional toolbars, you will want to clone and modify the command handler and the update\-command UI handler for this command.  
  
-   ID\_VIEW\_STATUS\_BAR   Toggles the status bar on and off  
  
     This command is implemented in `CFrameWnd` just like **ID\_VIEW\_TOOLBAR**, except a different child window ID \(**AFX\_IDW\_STATUS\_BAR**\) is used.  
  
## Update\-Only Command Handlers  
 Several standard command IDs are used as indicators in status bars.  These use the same update\-command UI handling mechanism to display their current visual state during application idle time.  Since they can't be selected by the user \(that is, you cannot push a status bar pane\), then it makes no sense to have an `ON_COMMAND` handler for these command IDs.  
  
-   **ID\_INDICATOR\_CAPS** : CAP lock indicator.  
  
-   **ID\_INDICATOR\_NUM** : NUM lock indicator.  
  
-   **ID\_INDICATOR\_SCRL** : SCRL lock indicator.  
  
-   **ID\_INDICATOR\_KANA** : KANA lock indicator \(applicable only to Japanese systems\).  
  
 All three of these are implemented in **CFrameWnd::OnUpdateKeyIndicator**, an implementation helper that uses the command ID to map to the appropriate Virtual Key.  A common implementation enables or disables \(for status panes disabled \= no text\) the `CCmdUI` object depending on whether the appropriate Virtual Key is currently locked.  
  
 Customization of this command handler is not recommended.  
  
-   **ID\_INDICATOR\_EXT : EXT**ended select indicator.  
  
-   **ID\_INDICATOR\_OVR : OV**e**R**strike indicator.  
  
-   **ID\_INDICATOR\_REC : REC**ording indicator.  
  
 Currently there is no standard implementation for these indicators.  
  
 If you choose to implement these indicators, we recommend you use these indicator IDs and maintaining the ordering of the indicators in your status bar \(that is, in this order: EXT, CAP, NUM, SCRL, OVR, REC\).  
  
## 참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)
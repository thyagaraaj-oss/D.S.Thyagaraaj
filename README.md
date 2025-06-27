 

SOURCE CODE: 

.APP PY 

function varargout = Design_GUI(varargin) 

% DESIGN_GUI MATLAB code for Design_GUI.fig 

%      DESIGN_GUI, by itself, creates a new DESIGN_GUI or raises the existing 

%      singleton*. 

% 

%      H = DESIGN_GUI returns the handle to a new DESIGN_GUI or the handle to 

%      the existing singleton*. 

% 

%      DESIGN_GUI('CALLBACK',hObject,eventData,handles,...) calls the local 

%      function named CALLBACK in DESIGN_GUI.M with the given input arguments. 

% 

%      DESIGN_GUI('Property','Value',...) creates a new DESIGN_GUI or raises the 

%      existing singleton*.  Starting from the left, property value pairs are 

%      applied to the GUI before Design_GUI_OpeningFcn gets called.  An 

%      unrecognized property name or invalid value makes property application 

%      stop.  All inputs are passed to Design_GUI_OpeningFcn via varargin. 

% 

%      *See GUI Options on GUIDE's Tools menu.  Choose "GUI allows only one 

%      instance to run (singleton)". 

% 

% See also: GUIDE, GUIDATA, GUIHANDLES 

 

% Edit the above text to modify the response to help Design_GUI 

 

% Last Modified by GUIDE v2.5 22-Mar-2025 13:05:00 

 

% Begin initialization code - DO NOT EDIT 

gui_Singleton = 1; 

gui_State = struct('gui_Name',       mfilename, ... 

                   'gui_Singleton',  gui_Singleton, ... 

                   'gui_OpeningFcn', @Design_GUI_OpeningFcn, ... 

                   'gui_OutputFcn',  @Design_GUI_OutputFcn, ... 

                   'gui_LayoutFcn',  [] , ... 

                   'gui_Callback',   []); 

if nargin && ischar(varargin{1}) 

    gui_State.gui_Callback = str2func(varargin{1}); 

end 

 

if nargout 

    [varargout{1:nargout}] = gui_mainfcn(gui_State, varargin{:}); 

else 

    gui_mainfcn(gui_State, varargin{:}); 

end 

% End initialization code - DO NOT EDIT 

 

 

% --- Executes just before Design_GUI is made visible. 

function Design_GUI_OpeningFcn(hObject, eventdata, handles, varargin) 

% This function has no output args, see OutputFcn. 

% hObject    handle to figure 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

% varargin   command line arguments to Design_GUI (see VARARGIN) 

 

% Choose default command line output for Design_GUI 

handles.output = hObject; 

axes(handles.axes1); axis off 

axes(handles.axes2); axis off 

axes(handles.axes3); axis off 

axes(handles.axes6); axis off 

% axes(handles.axes7); axis off 

axes(handles.axes10); axis off 

axes(handles.axes9); axis off 

 

set(handles.edit14,'String','--'); 

set(handles.edit15,'String','--'); 

set(handles.edit16,'String','--'); 

set(handles.edit17,'String','--'); 

set(handles.edit18,'String','--'); 

set(handles.edit19,'String','--'); 

 

set(handles.edit26,'String','**'); 

set(handles.edit27,'String','**'); 

set(handles.edit28,'String','**'); 

set(handles.edit29,'String','**'); 

set(handles.edit30,'String','**'); 

set(handles.edit31,'String','**'); 

% set(handles.edit32,'String','**'); 

% Update handles structure 

guidata(hObject, handles); 

 

% UIWAIT makes Design_GUI wait for user response (see UIRESUME) 

% uiwait(handles.figure1); 

 

 

% --- Outputs from this function are returned to the command line. 

function varargout = Design_GUI_OutputFcn(hObject, eventdata, handles)  

% varargout  cell array for returning output args (see VARARGOUT); 

% hObject    handle to figure 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Get default command line output from handles structure 

varargout{1} = handles.output; 

 

 

 

function edit1_Callback(hObject, eventdata, handles) 

% hObject    handle to edit1 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit1 as text 

%        str2double(get(hObject,'String')) returns contents of edit1 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit1_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit1 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

 

function edit2_Callback(hObject, eventdata, handles) 

% hObject    handle to edit2 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit2 as text 

%        str2double(get(hObject,'String')) returns contents of edit2 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit2_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit2 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

% --- Executes on button press in pushbutton1. 

function pushbutton1_Callback(hObject, eventdata, handles) 

% hObject    handle to pushbutton1 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

global a;global inp; 

    [fname path]=uigetfile({'*.*';'*.bmp';'*.tif';'*.jpg'},'Browse Image'); 

  

if fname~=0 

    img=imread([path,fname]); 

    axes(handles.axes1); imshow(img); title('Input Image'); 

%     set(handles.text13,'String',fname) 

    a=img; 

    inp=a; 

else 

    warndlg('Please Select the necessary Image File'); 

end 

 

% --- Executes on button press in pushbutton3. 

function pushbutton3_Callback(hObject, eventdata, handles) 

% hObject    handle to pushbutton3 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA). 

global a;global I3;global I; 

 

I=a; 

axes(handles.axes2); imshow(I); title('Gray Image'); 

pause(1); 

I2 = imtophat(I,strel('disk',15)); 

I3 = histeq(I2); 

axes(handles.axes2); imshow(I3);title('Increase the Image Contrast'); 

 

 

 

 

% --- Executes on button press in pushbutton4. 

function pushbutton4_Callback(hObject, eventdata, handles) 

% hObject    handle to pushbutton4 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

global a;global I;global datass; 

s=a; 

num_iter = 10; 

    delta_t = 1/7; 

    kappa = 15; 

    option = 2; 

    inp = anisodiff(s,num_iter,delta_t,kappa,option); 

    inp = uint8(inp); 

     

inp=imresize(inp,[256,256]); 

if size(inp,3)>1 

    inp=rgb2gray(inp); 

end 

I3=inp; 

sout=imresize(inp,[256,256]); 

t0=60; 

th=t0+((max(inp(:))+min(inp(:)))./2); 

for i=1:1:size(inp,1) 

    for j=1:1:size(inp,2) 

        if inp(i,j)>th 

            sout(i,j)=1; 

        else 

            sout(i,j)=0; 

        end 

    end 

end 

label=bwlabel(sout) 

stats=regionprops(logical(sout),'Solidity','Area','BoundingBox'); 

density=[stats.Solidity]; 

area=[stats.Area]; 

high_dense_area=density>0.6; 

max_area=max(area(high_dense_area)); 

 

 

if max_area>100 

else 

msgbox('Normal!!','status'); 

axes(handles.axes3); cla(handles.axes3); title(''); axis off 

axes(handles.axes6); cla(handles.axes6); title(''); axis off 

    return; 

end 

datass_label=find(area==max_area); 

datass=ismember(label,datass_label); 

box = stats(datass_label); 

wantedBox = box.BoundingBox; 

dilationAmount = 5; 

rad = floor(dilationAmount); 

[r,c] = size(datass); 

filledImage = imfill(datass, 'holes'); 

 

for i=1:r 

   for j=1:c 

       x1=i-rad; 

       x2=i+rad; 

       y1=j-rad; 

       y2=j+rad; 

       if x1<1 

           x1=1; 

       end 

       if x2>r 

           x2=r; 

       end 

       if y1<1 

           y1=1; 

       end 

       if y2>c 

           y2=c; 

       end 

       erodedImage(i,j) = min(min(filledImage(x1:x2,y1:y2))); 

   end 

end 

datassOutline=datass; 

datassOutline(erodedImage)=0; 

rgb = inp(:,:,[1 1 1]); 

red = rgb(:,:,1); 

red(datassOutline)=255; 

green = rgb(:,:,2); 

green(datassOutline)=0; 

blue = rgb(:,:,3); 

blue(datassOutline)=0; 

datassOutlineInserted(:,:,1) = red;  

datassOutlineInserted(:,:,2) = green;  

datassOutlineInserted(:,:,3) = blue;  

axes(handles.axes6); imshow(inp); title('Segmented Image'); 

hold on;rectangle('Position',wantedBox,'EdgeColor','y');hold off; 

 

 

 

 

% --- Executes on button press in pushbutton5. 

function pushbutton5_Callback(hObject, eventdata, handles) 

% hObject    handle to pushbutton5 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

 

% --- Executes on button press in pushbutton6. 

function pushbutton6_Callback(hObject, eventdata, handles) 

% hObject    handle to pushbutton6 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

axes(handles.axes1); cla(handles.axes1); title(''); axis off 

axes(handles.axes2); cla(handles.axes2); title(''); axis off 

axes(handles.axes3); cla(handles.axes3); title(''); axis off 

axes(handles.axes6); cla(handles.axes6); title(''); axis off 

% axes(handles.axes7); cla(handles.axes7); title(''); axis off 

axes(handles.axes9); cla(handles.axes9); title(''); axis off 

axes(handles.axes10); cla(handles.axes10); title(''); axis off 

 

set(handles.edit14,'String','**'); 

set(handles.edit15,'String','**'); 

set(handles.edit16,'String','**'); 

set(handles.edit17,'String','**'); 

set(handles.edit18,'String','**'); 

set(handles.edit19,'String','**'); 

 

set(handles.edit20,'String','**'); 

set(handles.edit21,'String','**'); 

set(handles.edit22,'String','**'); 

set(handles.edit23,'String','**'); 

set(handles.edit12,'String','**'); 

set(handles.edit24,'String','**'); 

set(handles.edit25,'String','**'); 

 

 

set(handles.edit26,'String','**'); 

set(handles.edit27,'String','**'); 

set(handles.edit28,'String','**'); 

set(handles.edit29,'String','**'); 

set(handles.edit30,'String','**'); 

set(handles.edit31,'String','**'); 

% set(handles.edit32,'String','**'); 

 

 

 

 

% --- Executes on button press in pushbutton7. 

function pushbutton7_Callback(hObject, eventdata, handles) 

% hObject    handle to pushbutton7 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

close Brain_datass 

 

 

 

function edit4_Callback(hObject, eventdata, handles) 

% hObject    handle to edit4 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit4 as text 

%        str2double(get(hObject,'String')) returns contents of edit4 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit4_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit4 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

 

function edit5_Callback(hObject, eventdata, handles) 

% hObject    handle to edit5 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit5 as text 

%        str2double(get(hObject,'String')) returns contents of edit5 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit5_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit5 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

 

function edit3_Callback(hObject, eventdata, handles) 

% hObject    handle to edit3 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit3 as text 

%        str2double(get(hObject,'String')) returns contents of edit3 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit3_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit3 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

% --- Executes on button press in pushbutton8. 

function pushbutton8_Callback(hObject, eventdata, handles) 

% hObject    handle to pushbutton8 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

run('Analysis_Data.p'); 

 

 

function edit6_Callback(hObject, eventdata, handles) 

% hObject    handle to edit6 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit6 as text 

%        str2double(get(hObject,'String')) returns contents of edit6 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit6_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit6 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

 

function edit7_Callback(hObject, eventdata, handles) 

% hObject    handle to edit7 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit7 as text 

%        str2double(get(hObject,'String')) returns contents of edit7 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit7_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit7 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

 

function edit10_Callback(hObject, eventdata, handles) 

% hObject    handle to edit10 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit10 as text 

%        str2double(get(hObject,'String')) returns contents of edit10 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit10_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit10 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

 

function edit11_Callback(hObject, eventdata, handles) 

% hObject    handle to edit11 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit11 as text 

%        str2double(get(hObject,'String')) returns contents of edit11 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit11_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit11 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

 

function edit12_Callback(hObject, eventdata, handles) 

% hObject    handle to edit12 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit12 as text 

%        str2double(get(hObject,'String')) returns contents of edit12 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit12_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit12 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

 

function edit13_Callback(hObject, eventdata, handles) 

% hObject    handle to edit13 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit13 as text 

%        str2double(get(hObject,'String')) returns contents of edit13 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit13_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit13 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

 

function edit20_Callback(hObject, eventdata, handles) 

% hObject    handle to edit20 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit20 as text 

%        str2double(get(hObject,'String')) returns contents of edit20 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit20_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit20 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

 

function edit27_Callback(hObject, eventdata, handles) 

% hObject    handle to edit27 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit27 as text 

%        str2double(get(hObject,'String')) returns contents of edit27 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit27_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit27 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

 

function edit26_Callback(hObject, eventdata, handles) 

% hObject    handle to edit26 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    structure with handles and user data (see GUIDATA) 

 

% Hints: get(hObject,'String') returns contents of edit26 as text 

%        str2double(get(hObject,'String')) returns contents of edit26 as a double 

 

 

% --- Executes during object creation, after setting all properties. 

function edit26_CreateFcn(hObject, eventdata, handles) 

% hObject    handle to edit26 (see GCBO) 

% eventdata  reserved - to be defined in a future version of MATLAB 

% handles    empty - handles not created until after all CreateFcns called 

 

% Hint: edit controls usually have a white background on Windows. 

%       See ISPC and COMPUTER. 

if ispc && isequal(get(hObject,'BackgroundColor'), get(0,'defaultUicontrolBackgroundColor')) 

    set(hObject,'BackgroundColor','white'); 

end 

 

 

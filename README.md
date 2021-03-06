# WMs-Herbstluftwm
Configuraçoes pessoais da WM "herbstluftwm", juntamente com suas respectivas ferramentas e dependencias

# Aplicaçoẽs usadas
			picom
		Para a transparencia
			Rofi
		Para os menus
			Polybar
		Para a barra
			zsh
		Shell do terminal
			ranger
		Navegador de arquivos,via terminal
			feh
		Exibir imagens e setar planos de fundo
			viewnior
		Exibir imagens derivadas de prints da tela
			scrot
		Tirar prints da tela
			mplayer
		Reproduzir imagens
			ffmpegthumbnailer
		Exibir imagens de videos dentro do ranger
			w3m
		Exibir imagens de arquivos dentro do ranger

# Apresentação 

![alt text](https://github.com/Cesare-cesare/WMs-Herbstluftwm/blob/master/Wallpapers/wall.png)

O herbstluftwm é um gerenciador de janelas lado a lado para o X11 usando o Xlib. Suas principais características podem ser descritas com:

o layout é baseado na divisão de quadros em sub-quadros que podem ser divididos novamente ou preenchidos com janelas (semelhante ao i3 / ou musca)

tags (ou áreas de trabalho ou áreas de trabalho virtuais ou ...) podem ser adicionadas / removidas em tempo de execução. Cada tag contém um próprio layout

exatamente uma tag é visualizada em cada monitor. As tags são independentes do monitor (semelhante ao xmonad )

Ele é configurado em tempo de execução através de chamadas ipc do herbstclient. Portanto, o arquivo de configuração é apenas um script que é executado na inicialização. (semelhante à wmii ou musca).

# Instalação

![alt text](https://github.com/Cesare-cesare/WMs-Herbstluftwm/blob/master/Examples/image.png)

A instalação e a configuração seguem duas etapas simples.

	Primeira etapa. A instalação
		sudo pacman -S herbstluftwm

	Segunda etapa. A configuração
		mkdir .config/herbstluftwm
		cp /etc/xdg/herbstluftwm .config/herbstluftwm

# A configuração em si.

![alt text](https://github.com/Cesare-cesare/WMs-Herbstluftwm/blob/master/Examples/image2.png)

Com um editor de textos de sua preferencia, edite o arquivo que estara contido dentro do .config/herbstluftwm,
com o nome de autostart.

Este arquivo pode ser dividido em 3 partes simples
	
	Primeira	
		Os programas que iniciam com o sistema
			Dentro deste bloco voce deve por os programas que
			deseja que iniciem no momento do boot de maneira altomatica
		
		Exemplos
				xsetroot -solid '#5A8E3A'
				setxkbmap -model abnt2 -layout br -variant abnt2 &
				sh ~/.fehbg &
				polybar -r mybar & 

	Segundo		
		Os atalhos do teclado
			Neste bloco, voce deve criar ou editar os atalhos do teclado de acordo com o seu uso
		
		Exemplos
				hc keybind $Mod-Shift-c spawn chromium
				hc keybind $Mod-Shift-f spawn chromium faceboock.com
				hc keybind $Mod-Shift-y spawn chromium youtube.com
				hc keybind $Mod-Shift-n spawn nemo
				hc keybind Print spawn scrot 'My_i3-gaps_%a-%d%b%y_%H.%M.png' -e 'viewnior ~/$f'
				hc keybind $Mod-Shift-s spawn subl
	Terceio		
		Os temas das janelas
			Neste bloco, voce pode mudar as cores e o comportamento das janelas.
			
			Exemplos
				hc attr theme.tiling.reset 1
				hc attr theme.floating.reset 1
				hc set frame_border_active_color '#FF4040'
				hc set frame_border_normal_color '#ff0000'
				hc set frame_bg_normal_color '#FF4040'
				hc set frame_bg_active_color '#FF4040'
				hc set frame_border_width 0

# Como usar essas configuraçoes das imagens?

	Para usar as configuraçoes das imagens, voce deve seguir alguns passos bem simples.

	Primeiro. Clone o repositorio

	Segundo. Mover os diretorios
			cd WMs-Herbstluftwm
			cp -r herbstluftwm ~/.config
			cp -r rofi ~/.config
			cp -r polybar ~/.config
			cp -r rofi ~/.config

	Terceiro. Mover as fontes
			cd fonts
			cp -r * /usr/share/fonts

	Quarto. Wallpapers
			Se voce quiser usar as imagens da customização,
			basta ter o feh instalado e usar umas delas.

# Rofi 

O rofi e usado para abrir tres menus.
Um de programas e outro para as janelas abertas

Para usar o menu tecle Super+d
Para usar o menu de janelas tecle Super+Tab 
Para usar o PoweMenu tecle Super+F1

# Menu de aplicativos

![alt text](https://github.com/Cesare-cesare/WMs-Herbstluftwm/blob/master/Examples/example004.jpg)

# Menu de janelas abertas

![alt text](https://github.com/Cesare-cesare/WMs-Herbstluftwm/blob/master/Examples/example003.jpg)

# PowerMenu

![alt text](https://github.com/Cesare-cesare/WMs-Herbstluftwm/blob/master/Examples/example006.png)

# Polybar

O polybar e uma barra, que pode ser usada de varias formas.
Para exibir informaçoes do sistema, ou ate mesmo para abrir aplicaçoes

![alt text](https://github.com/Cesare-cesare/WMs-Herbstluftwm/blob/master/Examples/example002.jpg)

Caso voce nao saiba como instalar o polybar. Basta clonala do repositorio AUR com 
git clone https://aur.archlinux.org/polybar.git

Em seguida entra no diretorio pertencente ao polybar e dar o comando

	makepkg -si

Entao e so aguardar a instalaçao.

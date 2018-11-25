# LEARN SRE README

My goal is to complete software engineering within the coming year. The expected target is to finish the goal by Dec 2019 and sooner start applying for jobs.

I always love to code. But because of my procarstination, kids and other financial stuff I was mainly lazying around doing tasks at very slow pace.

I am already working in a firm from last 10 years, but i would like to pursue my skills further, apply for better jobs with better oppurtunities.

Tasks:
26/11/2018
Start the Course CS 101 from Udacity.
eDx: CS 50 Course.

So to start with.
With my present job, I am going to start and finish my CS101(Udacity) and CS50(eDX) courses.


I will begin with my setup first.

I am going to primarily use emacs for my development work and here is my init.el

```
(setq inhibit-startup-message t)
(setq package-archives '(("gnu" . "https://elpa.gnu.org/packages/")
			 ("marmalade" . "https://marmalade-repo.org/packages/")
			 ("melpa" . "https://melpa.org/packages/")
			 ("elpy" . "https://jorgenschaefer.github.io/packages/")))
(package-initialize)
(when (not package-archive-contents)
  (package-refresh-contents))
(defvar myPackages
  '(better-defaults
    ein
    elpy
    flycheck
    material-theme
    py-autopep8))

(mapc #'(lambda (package)
	  (unless (package-installed-p package)
	    (package-install package)))
      myPackages)

(ido-mode)
(load-theme 'material t)
(elpy-enable)

(add-hook 'css-mode-hook 'my-css-mode-hook)
(defun my-css-mode-hook ()
  (rainbow-mode 1))
(put 'upcase-region 'disabled nil)

(defun now()
  "insert string for the current time format like '2:34 PM' or 1507121460"
  (interactive) ; Permit invocation in minibuffer
  (insert (format-time-string "%02y%02m%02d%02H%02M")))

(defun today ()
  "Insert string for the current time formated in Indian Style., w.g. Sunday, Spetember 17, 2000 or standard 17-09-2000."
  (interactive)
  (insert (format-time-string "%d-%m-%y")))

(setq python-shell-interpreter "ipython"
      python-shell-interpreter-args "-i --simple-prompt")

;; use flycheck not flymake with elpy
(when (require 'flycheck nil t)
  (setq elpy-modules (delq 'elpy-module-flymake elpy-modules))
  (add-hook 'elpy-mode-hook 'flycheck-mode))

;; enable autopep8 formatting on save
(require 'py-autopep8)
(add-hook 'elpy-mode-hook 'py-autopep8-enable-on-save)
(provide 'init)
;;;init.el ends here
```

With this, i would be using magit to commit my code to github.

I need to keep updating this document to track my progress.


Resources:
The follwing courses will help me with my task

Curated list of study Material: https://github.com/jwasham/coding-interview-university
Another original copy is: https://github.com/omps/coding-interview-university
https://techdevguide.withgoogle.com/ - Google Technical Guide
www.freecodecamp.org
You Won't remember all: https://startupnextdoor.com/retaining-computer-science-knowledge/

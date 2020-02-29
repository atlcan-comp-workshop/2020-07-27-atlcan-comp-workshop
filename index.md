---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "swc"    # what kind of Carpentry (must be either "lc" or "dc" or "swc").
                      # Be sure to update the Carpentry type in _config.yml as well.
venue: "University of Victoria"        # brief name of host site without address (e.g., "Euphoric State University")
address: "3800 Finnerty Rd, Victoria, BC, Canada V8P 5C2"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "us"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latlng: "48.462623, -123.310004"       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use https://www.latlong.net/)
humandate: "July 27-31, 2019"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "9:00 AM - 5:00 PM"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: "2020-07-27"      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: "2019-07-31"        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Justin Chiu", "Bingxuan Liu", "Rolf Seuster", "Giordon Stark"]
helper: ["Bob Kowalewski", "Nils Krumnack", "Michel Lefebvre", "Alison Lister", "Danika MacDonell", "Samuel Meehan", "Luke Polson"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["danikam1@uvic.ca"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:             # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
HEADER

Edit the values in the block above to be appropriate for your workshop.
If the value is not 'true', 'false', 'null', or a number, please use
double quotation marks around the value, unless specified otherwise.
And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

{% if page.carpentry != site.carpentry %}
<div class="alert alert-warning">
You specified <code>carpentry: {{page.carpentry}}</code> in <code>index.md</code> and
<code>carpentry: {{site.carpentry}}</code> in <code>_config.yml</code>. Make sure you edit both files. After editing <code>_config.yml</code>, you need to run <code>make serve</code> again to
see the changes take effect locally.
</div>
{% endif %}

{% comment %}
EVENTBRITE

This block includes the Eventbrite registration widget if
'eventbrite' has been set in the header.  You can delete it if you
are not using Eventbrite, or leave it in, since it will not be
displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
{% endcomment %}
{% if page.carpentry == "swc" %}
{% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
{% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
{% include lc/intro.html %}
{% endif %}

<h2 id="nitty-gritty">Nitty Gritty Details</h2>

{% comment %}
AUDIENCE

Explain who your audience is.  (In particular, tell readers if the
workshop is only open to people from a particular institution.
{% endcomment %}
{% if page.carpentry == "swc" %}
{% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
{% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
{% include lc/who.html %}
{% endif %}

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. They should have a few specific software packages installed (listed <a href="#setup">below</a>). <em><strong><font color="red"> It is highly recommended that you DO NOT choose to use Windows.  If you currently have a windows machine, please make it dual boot with Linux -</font>
  <a href="https://opensource.com/article/18/5/dual-boot-linux">follow these instructions</a>.  </strong></em>
</p>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<p id="code-of-conduct">
<strong>Code of Conduct:</strong>  Everyone who participates in Carpentries activities is required to conform to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>. This document also outlines how to report an incident if needed.
</p>


{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
<strong>Accessibility:</strong> We are committed to making this workshop
accessible to everybody.
The workshop organizers have checked that:
</p>
<ul>
<li>The room is wheelchair / scooter accessible.</li>
<li>Accessible restrooms are available.</li>
</ul>
<p>
If we can help making learning easier for
you (e.g. sign-language interpreters, lactation facilities) please
get in touch (using contact details below) and we will
attempt to provide them. 
</p>

<p>
If you are interested in attending the workshop but unable to due to a lack of funds, contact us with details of your funding requirements and we may be able to provide some assistance on a case-by-case basis. 
</p>

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.



{% comment %}
SCHEDULE

Show the workshop's schedule.  Edit the items and times in the table
to match your plans.  You may also want to change 'Day 1' and 'Day
2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

{% if page.carpentry == "swc" %}
{% include sc/schedule.html %}
{% elsif page.carpentry == "dc" %}
{% include dc/schedule.html %}
{% elsif page.carpentry == "lc" %}
{% include lc/schedule.html %}
{% endif %}

{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

http://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>


<!--{% comment %}
SYLLABUS

Show what topics will be covered.

1. If your workshop is R rather than Python, remove the comment
around that section and put a comment around the Python section.
2. Some workshops will delete SQL.
3. Please make sure the list of topics is synchronized with what you
intend to teach.
4. You may need to move the div's with class="col-md-6" around inside
the div's with class="row" to balance the multi-column layout.

This is one of the places where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}
<h2 id="syllabus">Syllabus</h2>

{% if page.carpentry == "swc" %}
{% include sc/syllabus.html %}
{% elsif page.carpentry == "dc" %}
{% include dc/syllabus.html %}
{% elsif page.carpentry == "lc" %}
{% include lc/syllabus.html %}
{% endif %}
-->

<hr/>

{% comment %}
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>

<p>
  To participate in a
  {% if page.carpentry == "swc" %}
  Software Carpentry
  {% elsif page.carpentry == "dc" %}
  Data Carpentry
  {% elsif page.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  workshop,
  you will need access to the software described below.
  In addition, you will need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

<p>
  If you are using macOS, you are highly recommended to use <a href="https://brew.sh">Homebrew</a>, a package manager for macOS.
</p>

<div id="shell"> {% comment %} Start of 'shell' section. {% endcomment %}
  <h3>The Bash Shell</h3>
  <p>
    Bash is a commonly-used shell that gives you the power to do simple
    tasks more quickly.
  </p>

  <div>
    <ul class="nav nav-tabs nav-justified" role="tablist">
      <li role="presentation" class="active"><a data-os="windows" href="#shell-windows" aria-controls="Windows" role="tab" data-toggle="tab">Windows</a></li>
      <li role="presentation"><a data-os="macos" href="#shell-macos" aria-controls="MacOS" role="tab" data-toggle="tab">MacOS</a></li>
      <li role="presentation"><a data-os="linux" href="#shell-linux" aria-controls="Linux" role="tab" data-toggle="tab">Linux</a></li>
    </ul>

    <div class="tab-content">
      <article role="tabpanel" class="tab-pane active" id="shell-windows">
        <a href="https://www.youtube.com/watch?v=339AEqk9c-8">Video Tutorial</a>
        <ol>
          <li>Download the Git for Windows <a href="https://git-for-windows.github.io/">installer</a>.</li>
          <li>Run the installer and follow the steps below:
            <ol>
              {% comment %} Git 2.18.0 Setup {% endcomment %}
              <li>
                Click on "Next" four times (two times if you've previously
                installed Git).  You don't need to change anything
                in the Information, location, components, and start menu screens.
              </li>
              <li>
                <strong>
                  Select "Use the nano editor by default" and click on "Next".
                </strong>
              </li>
              {% comment %} Adjusting your PATH environment {% endcomment %}
              <li>
                Keep "Use Git from the Windows Command Prompt" selected and click on "Next".
                If you forgot to do this programs that you need for the workshop will not work properly.
                If this happens rerun the installer and select the appropriate option.
              </li>
              {% comment %} Choosing the SSH executable {% endcomment %}
              <li>Click on "Next".</li>
              {% comment %} Configuring the line ending conversions {% endcomment %}
              <li>
                Keep "Checkout Windows-style, commit Unix-style line endings" selected and click on "Next".
              </li>
              {% comment %} Configuring the terminal emulator to use with Git Bash {% endcomment %}
              <li>
                <strong>
                  Select "Use Windows' default console window" and click on "Next".
                </strong>
              </li>
              {% comment %} Configuring experimental performance tweaks {% endcomment %}
              <li>Click on "Install".</li>
              {% comment %} Installing {% endcomment %}
              {% comment %} Completing the Git Setup Wizard {% endcomment %}
              <li>Click on "Finish".</li>
            </ol>
          </li>
          <li>
            If your "HOME" environment variable is not set (or you don't know what this is):
            <ol>
              <li>Open command prompt (Open Start Menu then type <code>cmd</code> and press [Enter])</li>
              <li>
                Type the following line into the command prompt window exactly as shown:
                <p><code>setx HOME "%USERPROFILE%"</code></p>
              </li>
              <li>Press [Enter], you should see <code>SUCCESS: Specified value was saved.</code></li>
              <li>Quit command prompt by typing <code>exit</code> then pressing [Enter]</li>
            </ol>
          </li>
        </ol>
        <p>This will provide you with both Git and Bash in the Git Bash program.</p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="shell-macos">
        <p>
          The default shell in all versions of macOS is Bash, so no
          need to install anything.  You access Bash from the Terminal
          (found in
          <code>/Applications/Utilities</code>).
          See the Git installation <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a>
          for an example on how to open the Terminal.
          You may want to keep
          Terminal in your dock for this workshop. Many macOS users perfer <a href="https://iterm2.com">iTerm2</a>, use <code>brew cask install iterm2</code> to install with Homebrew.
        </p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="shell-linux">
        <p>
          The default shell is usually Bash, but if your
          machine is set up differently you can run it by opening a
          terminal and typing <code>bash</code>.  There is no need to
          install anything.
        </p>
      </article>
    </div>
  </div>
</div> {% comment %} End of 'shell' section. {% endcomment %}

<div id="git"> {% comment %} Start of 'Git' section. GitHub browser compatability
  is given at https://help.github.com/articles/supported-browsers/{% endcomment %}
  <h3>Git</h3>
  <p>
    Git is a version control system that lets you track who made changes
    to what when and has options for easily updating a shared or public
    version of your code
    on <a href="https://github.com/">github.com</a>. You will need a
    <a href="https://help.github.com/articles/supported-browsers/">supported
    web browser</a>.
  </p>
  <p>
    You will need an account at <a href="https://github.com/">github.com</a>
    for parts of the Git lesson. Basic GitHub accounts are free. We encourage
    you to create a GitHub account if you don't have one already.
    Please consider what personal information you'd like to reveal. For
    example, you may want to review these
    <a href="https://help.github.com/articles/keeping-your-email-address-private/">instructions
      for keeping your email address private</a> provided at GitHub.
  </p>

  <div>
    <ul class="nav nav-tabs nav-justified" role="tablist">
      <li role="presentation" class="active"><a data-os="windows" href="#git-windows" aria-controls="Windows" role="tab" data-toggle="tab">Windows</a></li>
      <li role="presentation"><a data-os="macos" href="#git-macos" aria-controls="MacOS" role="tab" data-toggle="tab">MacOS</a></li>
      <li role="presentation"><a data-os="linux" href="#git-linux" aria-controls="Linux" role="tab" data-toggle="tab">Linux</a></li>
    </ul>

    <div class="tab-content">
      <article role="tabpanel" class="tab-pane active" id="git-windows">
        <p>
          Git should be installed on your computer as part of your Bash
          install (described above).
        </p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="git-macos">
        <p>
          Git is part of the command-line tools for Xcode on macOS.
          Run in a terminal:
          <code>xcode-select --install</code>. This is needed for almost any
          development on macOS, since it includes your compilers. If you use homebrew,
          <code>brew install git</code> will get a slighly newer version.
          Optionally install Xcode from the Mac App Store.
        </p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="git-linux">
        <p>
          If Git is not already available on your machine you can try to
          install it via your distro's package manager. For Debian/Ubuntu run
          <code>sudo apt-get install git</code> and for Fedora run
          <code>sudo dnf install git</code>.
        </p>
      </article>
    </div>
  </div>
</div> {% comment %} End of 'Git' section. {% endcomment %}

<div id="editor"> {% comment %} Start of 'editor' section. {% endcomment %}
  <h3>Text Editor</h3>

  <p>
    When you're writing code, it's nice to have a text editor that is
    optimized for writing code, with features like automatic
    color-coding of key words. The default text editor on macOS and
    Linux is usually set to Vim, which is not famous for being
    intuitive. If you accidentally find yourself stuck in it, hit
    the <kbd>Esc</kbd> key, followed by <kbd>:</kbd>+<kbd>Q</kbd>+<kbd>!</kbd>
    (colon, lower-case 'q', exclamation mark), then hitting <kbd>Return</kbd> to
    return to the shell.
  </p>

  <div>
    <ul class="nav nav-tabs nav-justified" role="tablist">
      <li role="presentation" class="active"><a data-os="windows" href="#editor-windows" aria-controls="Windows" role="tab" data-toggle="tab">Windows</a></li>
      <li role="presentation"><a data-os="macos" href="#editor-macos" aria-controls="MacOS" role="tab" data-toggle="tab">MacOS</a></li>
      <li role="presentation"><a data-os="linux" href="#editor-linux" aria-controls="Linux" role="tab" data-toggle="tab">Linux</a></li>
    </ul>

    <div class="tab-content">
      <article role="tabpanel" class="tab-pane active" id="editor-windows">
        <p>
          nano is a basic editor and the default that instructors use in the workshop.
          It is installed along with Git.
        </p>
        <p>
          Others editors that you can use are
          <a href="https://notepad-plus-plus.org/">Notepad++</a> or
          <a href="https://www.sublimetext.com/">Sublime Text</a>.
          <strong>Be aware that you must
            add its installation directory to your system path.</strong>
          Please ask your instructor to help you do this.
        </p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="editor-macos">
        <p>
          nano is a basic editor and the default that instructors use in the workshop.
          See the Git installation <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a>
          for an example on how to open nano.
          It should be pre-installed. Many other editors are available in homebrew and homebrew cask.
        </p>
        <p>
          Others editors that you can use are
          <a href="https://www.barebones.com/products/bbedit/">BBEdit</a> or
          <a href="https://www.sublimetext.com/">Sublime Text</a>.
        </p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="editor-linux">
        <p>
          nano is a basic editor and the default that instructors use in the workshop.
          It should be pre-installed.
        </p>
        <p>
          Others editors that you can use are
          <a href="https://wiki.gnome.org/Apps/Gedit">Gedit</a>,
          <a href="https://kate-editor.org/">Kate</a> or
          <a href="https://www.sublimetext.com/">Sublime Text</a>.
        </p>
      </article>
    </div>
  </div>
</div> {% comment %} End of 'editor' section. {% endcomment %}

  <h3>Docker</h3>

  <p>
    <a href="https://www.docker.com/">Docker</a> is a powerful tool that allows you
    to perform a virtualization of your environment but completely in software.  It
    allows you to bundle up the installation of tools for use by others in a uniform way
    and we will be using it throughout the tutorial.  Installing docker is absolutely
    necessary and there are directions to do this in each operating system.  For those
    of you that are using a Windows operating system, if you already have docker running
    and are comfortable using it, that is fine.  However, if you do not, then be aware
    that its usage on Windows can be challenging and the instructor may not be able to
    help with setting it up during the tutorial. 
  </p>

<div id="DockerOS"> {% comment %} Start of 'DockerOS' section. {% endcomment %}
  <div>
    <ul class="nav nav-tabs nav-justified" role="tablist">
      <li role="presentation" class="active"><a data-os="windows" href="#docker-windows" aria-controls="Windows" role="tab" data-toggle="tab">Windows</a></li>
      <li role="presentation"><a data-os="macos" href="#docker-macos" aria-controls="MacOS" role="tab" data-toggle="tab">MacOS</a></li>
      <li role="presentation"><a data-os="linux" href="#docker-linux" aria-controls="Linux" role="tab" data-toggle="tab">Linux</a></li>
    </ul>

    <div class="tab-content">
      <article role="tabpanel" class="tab-pane active" id="docker-windows">
        <p>
          <font color="red">It is highly recommended that you</font> <strong> DO NOT </strong> <font color="red">use Windows.  Few individuals
          use this OS within the HEP community as most tools are designed for Unix-based systems.
          If you do have a Windows machine, consider making your computer a dual-boot machine </font>-
          <a href="https://opensource.com/article/18/5/dual-boot-linux">Link to Directions</a>
          <br/>
          <br/>
          Download Docker for Windows <a href="https://docs.docker.com/docker-for-windows/install/">instructions</a>.<br>
          <br/>
          Docker Desktop for Windows is the Community Edition (CE) of Docker for Microsoft Windows. To download Docker Desktop for Windows, head to <a href="https://hub.docker.com/editions/community/docker-ce-desktop-windows">Docker Hub</a>. <br>
          <br/>
          Please read the relevant information on these pages, it should take no more than 5 minutes.
          <br/>
        </p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="docker-macos">
        <p>
          <br/>
          Download Docker for MacOS <a href="https://docs.docker.com/docker-for-mac/install/">instructions</a>.<br>
          <br/>
          Docker is a full development platform for creating containerized apps, and Docker Desktop for Mac is the best way to get started with Docker on a Mac. To download Docker Desktop for MacOS, head to <a href="https://hub.docker.com/editions/community/docker-ce-desktop-mac">Docker Hub</a>. <br>
          <br/>
          Please read the relevant information on these pages, it should take no more than 5 minutes.
          <br/>
          Another common way to install packages on Mac OSX is via the <a href="https://brew.sh/">homebrew</a> package manager.  In the case of docker, you can easily install
          docker by setting up homebrew and executing <code>brew cask install docker</code>.
          <br/>
        </p>
      </article>
      <article role="tabpanel" class="tab-pane active" id="docker-linux">
        <p>
          <br/>
          Downloading and installing Docker for Linux may be slightly more difficult but please contact the organisers or tutors as soon as possible so they can help with any problems.<br>
          <br/>
          Here are the instructions for two popular Linux distributions:
          <li><a href="https://docs.docker.com/install/linux/docker-ce/CentOS/">CentOS</a></li>
          <li><a href="https://docs.docker.com/install/linux/docker-ce/ubuntu/">Ubuntu</a></li>
          <br/>
          Instructions for other Linux distributions can be found on the Docker docs pages.
          <br/>
          <br/>
          <font color="red">Be sure to read the Docker documentation on post-installation steps for Linux and managing Docker
          as a </font> <a href="https://docs.docker.com/install/linux/linux-postinstall/">non-root user</a>.
          <font color="red">This will allow you to edit files when you have started up the Docker container from your image. </font>
          <br/>
        </p>
      </article>
    </div>
  </div>
</div> {% comment %} End of 'docker' section. {% endcomment %}


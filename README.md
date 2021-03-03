# Abgeordnetenwatch Emails

### Augment Abgeordnetenwatch data to include Abgeordnete (representives) email

Processes the Bundestag-Abgeordnete.csv from https://www.abgeordnetenwatch.de/ and adds email addresses for each representative as accurately as possible

## Method

Creates email addresses based on first_name, last_name

This process tries to use the same convention as the Bundestag uses when forming email addresses.

All conventions are based on observation and may not be entirely correct.

### Observed conventions in email formatting:

- Hyphenated "-" last names such as Aschenberg-Dugnus

  Preserved in the email address
- Hyphenated "-" first names such as Leif-Erik

  Preserved in the email address
- All accented characters "äéöüß" are converted

  See accent_aliases dictionary below
- If there are multiple first names, there is no consistency to whether they are included or not and how. Most of the time the second name is just dropped, but not always.

  For these occurances, the known_emails lookup is used to explicity set the email address

- If a last name contains "von", there is no consistency to whether it is included or not and how.

  For these occurances, the known_emails lookup is used to explicity set the email address
- If a last name starts with "de " as in "de Vries" the "de" is preserved and the space removed

## Usage

_Free to use, duplicate, whatever._

Unzip contents of data zipfile to project directory then:

```
pip install -r requirements.txt
jupyter notebook
```
